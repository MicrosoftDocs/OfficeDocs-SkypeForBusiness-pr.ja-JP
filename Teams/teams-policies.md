---
title: Microsoft Teams でチームポリシーを管理する
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
description: 組織のチームポリシーを使用および管理して、チームとチャネルでユーザーが実行できる操作を制御する方法について説明します。
f1keywords:
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discoverteams
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.createchannels
- ms.teamsadmincenter.teams.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discover
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.create
ms.openlocfilehash: 02c7258ebc316d5e08c77698e18935eb51b5b43d
ms.sourcegitcommit: f2c7626dbef4ed250b9a937a9b56d46fe2e2039e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2019
ms.locfileid: "39998815"
---
# <a name="manage-teams-policies-in-microsoft-teams"></a><span data-ttu-id="8dcff-103">Microsoft Teams でチームポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="8dcff-103">Manage teams policies in Microsoft Teams</span></span>

<span data-ttu-id="8dcff-104">管理者は、Microsoft Teams のチームポリシーを使って、チームとチャネルで組織内のユーザーが実行できる操作を制御することができます。</span><span class="sxs-lookup"><span data-stu-id="8dcff-104">As an admin, you can use teams policies in Microsoft Teams to control what users in your organization can do in teams and channels.</span></span> <span data-ttu-id="8dcff-105">たとえば、検索結果とチームギャラリーでプライベートチームの検出を許可するかどうか、およびユーザーがプライベートチャネルの作成を許可されているかどうかを設定できます。</span><span class="sxs-lookup"><span data-stu-id="8dcff-105">For example, you can set whether users are allowed to discover private teams in search results and in the team gallery and whether users are allowed to create private channels.</span></span>

<span data-ttu-id="8dcff-106">チームポリシーを管理するには、Microsoft teams 管理センターで**teams** > **teams のポリシー**に移動します。</span><span class="sxs-lookup"><span data-stu-id="8dcff-106">You manage teams policies by going to **Teams** > **Teams policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="8dcff-107">グローバル (組織全体の既定) ポリシーを使用するか、カスタムポリシーを作成してユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="8dcff-107">You can use the global (Org-wide default) policy or create custom policies and assign them to users.</span></span> <span data-ttu-id="8dcff-108">組織内のユーザーは、カスタムポリシーを作成して割り当てる場合を除き、自動的にグローバルポリシーを取得します。</span><span class="sxs-lookup"><span data-stu-id="8dcff-108">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

<span data-ttu-id="8dcff-109">グローバルポリシーを編集するか、カスタムポリシーを作成して割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="8dcff-109">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="8dcff-110">ユーザーにカスタムポリシーが割り当てられている場合は、そのポリシーがユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="8dcff-110">If a user is assigned a custom policy, that policy applies to the user.</span></span> <span data-ttu-id="8dcff-111">ユーザーにカスタムポリシーが割り当てられていない場合は、グローバルポリシーがユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="8dcff-111">If a user isn't assigned a custom policy, the global policy applies to the user.</span></span> <span data-ttu-id="8dcff-112">グローバルポリシーを編集するか、ポリシーを割り当てると、変更が有効になるまで最大24時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="8dcff-112">After you edit the global policy or assign a policy, it can take up to 24 hours for changes to take effect.</span></span>

## <a name="create-a-custom-teams-policy"></a><span data-ttu-id="8dcff-113">カスタムチームポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="8dcff-113">Create a custom teams policy</span></span>

1. <span data-ttu-id="8dcff-114">Microsoft Teams 管理センターの左のナビゲーションで、[**チーム** > **チームのポリシー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="8dcff-114">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="8dcff-115">[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8dcff-115">Click **Add**.</span></span>
3. <span data-ttu-id="8dcff-116">ポリシーの名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="8dcff-116">Enter a name and description for the policy.</span></span>

    ![Teams のポリシー設定のスクリーンショット](media/teams-policies.png)
4. <span data-ttu-id="8dcff-118">目的の設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="8dcff-118">Choose the settings that you want:</span></span>

- <span data-ttu-id="8dcff-119">**プライベートチーム**を見つける<a name="discoverteams"></a> : この設定を有効にして、ユーザーが検索結果とチームギャラリーでプライベートチームを見つけられるようにします。</span><span class="sxs-lookup"><span data-stu-id="8dcff-119">**Discover private teams**:<a name="discoverteams"> </a> Turn on this setting to allow users to discover private teams in search results and in the team gallery.</span></span>
- <span data-ttu-id="8dcff-120">**プライベートチャネル**を作成<a name="createchannels"></a>する: この設定を有効にして、ユーザーがプライベートチャネルを作成できるようにします。</span><span class="sxs-lookup"><span data-stu-id="8dcff-120">**Create private channels**: <a name="createchannels"> </a>Turn on this setting to allow users to create private channels.</span></span>

5. <span data-ttu-id="8dcff-121">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8dcff-121">Click **Save**.</span></span>

## <a name="edit-a-teams-policy"></a><span data-ttu-id="8dcff-122">Teams のポリシーを編集する</span><span class="sxs-lookup"><span data-stu-id="8dcff-122">Edit a teams policy</span></span>

<span data-ttu-id="8dcff-123">グローバルポリシーまたは作成したカスタムポリシーを編集できます。</span><span class="sxs-lookup"><span data-stu-id="8dcff-123">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="8dcff-124">Microsoft Teams 管理センターの左のナビゲーションで、[**チーム** > **チームのポリシー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="8dcff-124">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="8dcff-125">ポリシー名の左側をクリックしてポリシーを選択し、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8dcff-125">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="8dcff-126">目的の設定をオンまたはオフにして、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8dcff-126">Turn on or turn off the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-teams-policy-to-users"></a><span data-ttu-id="8dcff-127">ユーザーにカスタムチームポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="8dcff-127">Assign a custom teams policy to users</span></span>

<span data-ttu-id="8dcff-128">Microsoft Teams 管理センターを使用して、ユーザー設定のポリシーを1人以上のユーザーまたは Skype for Business PowerShell モジュールに割り当てて、セキュリティグループや配布グループなどのユーザーグループにカスタムポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="8dcff-128">You can use the Microsoft Teams admin center to assign a custom policy to one or more users or the Skype for Business PowerShell module to assign a custom policy to groups of users, such as a security group or distribution group.</span></span>

### <a name="assign-a-custom-teams-policy-to-a-user"></a><span data-ttu-id="8dcff-129">ユーザーにカスタムのチームポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="8dcff-129">Assign a custom teams policy to a user</span></span>

1. <span data-ttu-id="8dcff-130">Microsoft Teams 管理センターの左のナビゲーションで、[**ユーザー**] に移動し、ユーザーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="8dcff-130">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click  the user.</span></span>
2. <span data-ttu-id="8dcff-131">[**ポリシー**] をクリックし、[**割り当てられたポリシー**] の横にある [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8dcff-131">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="8dcff-132">[**チームポリシー**] で、割り当てるポリシーを選択し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8dcff-132">Under **Teams policies**, select the policy you want to assign, and then click **Save**.</span></span>

<span data-ttu-id="8dcff-133">ユーザー設定のチームポリシーを一度に複数のユーザーに割り当てるには、「 [teams のユーザー設定を一括](edit-user-settings-in-bulk.md)して編集する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8dcff-133">To assign a custom teams policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="8dcff-134">または、次の操作も行うことができます。</span><span class="sxs-lookup"><span data-stu-id="8dcff-134">Or, you can also do the following:</span></span>

1. <span data-ttu-id="8dcff-135">Microsoft Teams 管理センターの左のナビゲーションで、[**チーム** > **チームのポリシー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="8dcff-135">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="8dcff-136">ポリシー名の左側をクリックして、ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="8dcff-136">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="8dcff-137">[**ユーザーの管理**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="8dcff-137">Select **Manage users**.</span></span>
4. <span data-ttu-id="8dcff-138">[**ユーザーの管理**] ウィンドウで、[表示名] または [ユーザー名] でユーザーを検索し、名前を選択して [**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8dcff-138">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="8dcff-139">追加するユーザーごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="8dcff-139">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="8dcff-140">ユーザーの追加が完了したら、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8dcff-140">When you're finished adding users, click **Save**.</span></span>

### <a name="assign-a-custom-teams-policy-to-users-in-a-group"></a><span data-ttu-id="8dcff-141">ユーザー設定のチームポリシーをグループ内のユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="8dcff-141">Assign a custom teams policy to users in a group</span></span>

<span data-ttu-id="8dcff-142">ユーザー設定のチームポリシーは、既に特定した複数のユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="8dcff-142">You may want to assign a custom teams policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="8dcff-143">たとえば、セキュリティグループ内のすべてのユーザーにポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="8dcff-143">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="8dcff-144">これを行うには、Azure Active Directory PowerShell for Graph モジュールと Skype for Business PowerShell モジュールに接続します。</span><span class="sxs-lookup"><span data-stu-id="8dcff-144">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="8dcff-145">PowerShell を使用して Teams を管理する方法の詳細については、「[Teams での PowerShell の概要](teams-powershell-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8dcff-145">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="8dcff-146">この例では、"マーケティングチームポリシー" というチームポリシーを、Contoso マーケティンググループのすべてのユーザーに割り当てています。</span><span class="sxs-lookup"><span data-stu-id="8dcff-146">In this example, we assign a teams policy called Marketing Teams Policy to all users in the Contoso Marketing group.</span></span>  

> [!NOTE]
> <span data-ttu-id="8dcff-147">「[単一の Windows PowerShell ウィンドウですべての Office 365 サービスに接続する](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)」の手順に従って、必ず最初に Azure Active Directory PowerShell for Graph モジュールと Skype for Business PowerShell モジュールに接続してください。</span><span class="sxs-lookup"><span data-stu-id="8dcff-147">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="8dcff-148">特定のグループの GroupObjectId を取得します。</span><span class="sxs-lookup"><span data-stu-id="8dcff-148">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso Marketing"
```
<span data-ttu-id="8dcff-149">指定したグループのメンバーを取得します。</span><span class="sxs-lookup"><span data-stu-id="8dcff-149">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="8dcff-150">グループ内のすべてのユーザーを特定のチームポリシーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="8dcff-150">Assign all users in the group to a particular teams policy.</span></span> <span data-ttu-id="8dcff-151">この例では、マーケティングチームポリシーについてご紹介します。</span><span class="sxs-lookup"><span data-stu-id="8dcff-151">In this example, it's Marketing Teams Policy.</span></span>
```
$members | ForEach-Object { Grant-CsTeamsChannelsPolicy -PolicyName "Marketing Teams Policy" -Identity $_.UserPrincipalName}
``` 
<span data-ttu-id="8dcff-152">グループ内のメンバー数によっては、このコマンドの実行に数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="8dcff-152">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8dcff-153">関連項目</span><span class="sxs-lookup"><span data-stu-id="8dcff-153">Related topics</span></span>

- [<span data-ttu-id="8dcff-154">Teams でプライベート チームの検索を管理する</span><span class="sxs-lookup"><span data-stu-id="8dcff-154">Manage discovery of private teams in Teams</span></span>](manage-discovery-of-private-teams.md)
- [<span data-ttu-id="8dcff-155">Teams のプライベートチャネル</span><span class="sxs-lookup"><span data-stu-id="8dcff-155">Private channels in Teams</span></span>](private-channels.md)
