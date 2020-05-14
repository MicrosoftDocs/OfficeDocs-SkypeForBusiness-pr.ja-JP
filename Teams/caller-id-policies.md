---
title: Microsoft Teams で発信者番号ポリシーを管理する
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.voice.callinglineid.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams で発信者番号ポリシーを使用および管理して、組織内の Teams ユーザーの発信者番号を変更またはブロックする方法について説明します。
ms.openlocfilehash: a4dbdbac0922bb475f47447a3cf8b2d0f001909c
ms.sourcegitcommit: a7c823f61d9ab88424bad924113d780ce11e509f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44224262"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a><span data-ttu-id="e2d82-103">Microsoft Teams で発信者番号ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="e2d82-103">Manage caller ID policies in Microsoft Teams</span></span>

>[!INCLUDE [new-feature-teams-admin-center](includes/new-feature-teams-admin-center.md)]

<span data-ttu-id="e2d82-104">管理者は、Microsoft Teams で発信者番号ポリシーを使用して、発信者番号 (発信回線 ID とも呼ばれます) を変更またはブロックできます。</span><span class="sxs-lookup"><span data-stu-id="e2d82-104">As an admin, you can use caller ID policies in Microsoft Teams to change or block the caller ID (also known as calling line ID).</span></span> <span data-ttu-id="e2d82-105">既定では、Teams ユーザーが PSTN 電話に電話をかけると、Teams ユーザーの電話番号が表示され、PSTN 発信者が Teams ユーザーに電話をかけると、PSTN 発信者の電話番号が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e2d82-105">By default, the phone number of Teams users can be seen when they make a call to a PSTN phone and the phone number of PSTN callers can be seen when they call a Teams user.</span></span> <span data-ttu-id="e2d82-106">発信者番号ポリシーを使用すると、組織内の Teams ユーザーの代替電話番号を表示したり、着信番号が表示されないようにブロックしたりできます。</span><span class="sxs-lookup"><span data-stu-id="e2d82-106">You can use caller ID policies to display an alternate phone number for Teams users in your organization or block an incoming number from being displayed.</span></span>

<span data-ttu-id="e2d82-107">たとえば、ユーザーが電話をかけるときに、ユーザーの電話番号の代わりに組織の代表電話番号が表示されるように発信者番号を変更できます。</span><span class="sxs-lookup"><span data-stu-id="e2d82-107">For example, when users make a call, you can change the caller ID to display your organization's main phone number instead of users' phone numbers.</span></span>

<span data-ttu-id="e2d82-108">発信者番号ポリシーを管理するには、Microsoft Teams 管理センターで **[音声]** > **[発信者番号ポリシー]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="e2d82-108">You manage caller ID policies by going to **Voice** > **Caller ID policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="e2d82-109">グローバル (組織全体の既定) ポリシーを使用することも、カスタム ポリシーを作成してユーザーに割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="e2d82-109">You can use the global (Org-wide default) policy or create custom policies and assign them to users.</span></span> <span data-ttu-id="e2d82-110">カスタム ポリシーを作成して割り当てていない場合、組織内のユーザーにはグローバル ポリシーが自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="e2d82-110">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

<span data-ttu-id="e2d82-111">グローバル ポリシーを編集するか、カスタム ポリシーを作成して割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="e2d82-111">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="e2d82-112">ユーザーにカスタム ポリシーが割り当てられると、そのポリシーがユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="e2d82-112">If a user is assigned a custom policy, that policy applies to the user.</span></span> <span data-ttu-id="e2d82-113">ユーザーにカスタム ポリシーが割り当てられない場合は、グローバル ポリシーがユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="e2d82-113">If a user isn't assigned a custom policy, the global policy applies to the user.</span></span>

## <a name="create-a-custom-caller-id-policy"></a><span data-ttu-id="e2d82-114">カスタム発信者番号ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="e2d82-114">Create a custom caller ID policy</span></span>

1. <span data-ttu-id="e2d82-115">Microsoft Teams 管理センターの左側のナビゲーションで、**[音声]** > **[発信者番号ポリシー]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="e2d82-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="e2d82-116">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2d82-116">Click **Add**.</span></span> <br>
<span data-ttu-id="e2d82-117">![管理センターの新しい [発信者番号ポリシー] ページのスクリーン ショット](media/caller-id-policies-add-policy.png)</span><span class="sxs-lookup"><span data-stu-id="e2d82-117">![Screenshot of new caller ID policy page in the admin center](media/caller-id-policies-add-policy.png)</span></span>
3. <span data-ttu-id="e2d82-118">ポリシーの名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="e2d82-118">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="e2d82-119">ここで、希望する設定を選びます。</span><span class="sxs-lookup"><span data-stu-id="e2d82-119">From here, choose the settings that you want:</span></span>

    - <span data-ttu-id="e2d82-120">**[Block incoming caller ID](着信した発信者番号をブロックする)**: この設定をオンにすると、着信した通話の発信者番号が表示されないようにブロックされます。</span><span class="sxs-lookup"><span data-stu-id="e2d82-120">**Block incoming caller ID**: Turn on this setting to block the caller ID of incoming calls from being displayed.</span></span>
    - <span data-ttu-id="e2d82-121">**発信者番号ポリシーを無効**にする: この設定を有効にすると、ユーザーがポリシーの設定を上書きして、呼び出し先の番号を表示するかどうかを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="e2d82-121">**Override the caller ID policy**: Turn on this setting to let users override the settings in the policy regarding displaying their number to callees or not.</span></span> <span data-ttu-id="e2d82-122">つまり、発信者番号を表示するかどうかをユーザー自身が選択できます。</span><span class="sxs-lookup"><span data-stu-id="e2d82-122">This means that users can choose whether to display their caller ID.</span></span> <span data-ttu-id="e2d82-123">詳細については、「[発信の発信者番号のエンドユーザーによる制御](https://docs.microsoft.com/microsoftteams/how-can-caller-id-be-used-in-your-organization#end-user-control-of-outbound-caller-id)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2d82-123">For more information, see [End user control of outbound caller ID](https://docs.microsoft.com/microsoftteams/how-can-caller-id-be-used-in-your-organization#end-user-control-of-outbound-caller-id).</span></span>
    - <span data-ttu-id="e2d82-124">**発信者**番号認識の代わりに、次のいずれかを選択して、ユーザーに表示される発信者番号を設定します。</span><span class="sxs-lookup"><span data-stu-id="e2d82-124">**Replace the caller ID with**: Set the caller ID to be displayed for users by selecting one of the following:</span></span>

        - <span data-ttu-id="e2d82-125">**[ユーザーの番号]**: ユーザーの番号を表示します。</span><span class="sxs-lookup"><span data-stu-id="e2d82-125">**User's number**: Displays the user's number.</span></span> 
        - <span data-ttu-id="e2d82-126">**[サービス番号]**: サービス電話番号が発信者番号として表示されるように設定できるようになります。</span><span class="sxs-lookup"><span data-stu-id="e2d82-126">**Service number**: Lets you set a service phone number to display as the caller ID.</span></span>
        - <span data-ttu-id="e2d82-127">**[匿名]**: 発信者番号が [匿名] として表示されます。</span><span class="sxs-lookup"><span data-stu-id="e2d82-127">**Anonymous**: Displays the caller ID as Anonymous.</span></span>

    - <span data-ttu-id="e2d82-128">**発信者番号をこのサービス番号に変更**します。ユーザーの発信者番号を置き換えるサービス番号を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2d82-128">**Replace the caller ID with this service number**: Choose a service number to replace the caller ID of users.</span></span> <span data-ttu-id="e2d82-129">このオプションは、[発信者番号認識**の代わり**に**サービス番号**] を選択した場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="e2d82-129">This option is available if you selected **Service number** in **Replace the caller ID with**.</span></span>

5. <span data-ttu-id="e2d82-130">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2d82-130">Click **Save**.</span></span>

## <a name="edit-a-caller-id-policy"></a><span data-ttu-id="e2d82-131">発信者番号ポリシーを編集する</span><span class="sxs-lookup"><span data-stu-id="e2d82-131">Edit a caller ID policy</span></span>

<span data-ttu-id="e2d82-132">グローバル ポリシー、または作成したカスタム ポリシーを編集できます。</span><span class="sxs-lookup"><span data-stu-id="e2d82-132">You can edit the global policy or any custom policies that you create.</span></span> 

1. <span data-ttu-id="e2d82-133">Microsoft Teams 管理センターの左側のナビゲーションで、**[音声]** > **[発信者番号ポリシー]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="e2d82-133">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="e2d82-134">ポリシー名の左側をクリックしてポリシーを選び、**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2d82-134">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="e2d82-135">目的に合わせて設定を変更したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2d82-135">Change the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-caller-id-policy-to-users"></a><span data-ttu-id="e2d82-136">カスタム発信者番号ポリシーをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="e2d82-136">Assign a custom caller ID policy to users</span></span>

<span data-ttu-id="e2d82-137">Microsoft Teams 管理センターを使用して、1 つ以上のユーザーまたは Skype for Business PowerShell モジュールにカスタム ポリシーを割り当てることで、セキュリティグループや配布グループなどのユーザーのグループにカスタム ポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="e2d82-137">You can use the Microsoft Teams admin center to assign a custom policy to one or more users or the Skype for Business PowerShell module to assign a custom policy to groups of users, such as a security group or distribution group.</span></span>

### <a name="assign-a-custom-caller-line-id-policy-to-a-user"></a><span data-ttu-id="e2d82-138">カスタム発信者回線 ID ポリシーをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="e2d82-138">Assign a custom caller line ID policy to a user</span></span>

1. <span data-ttu-id="e2d82-139">Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動してユーザーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2d82-139">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="e2d82-140">**[ポリシー]** をクリックし、**[割り当てられたポリシー]** の横にある **[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2d82-140">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="e2d82-141">**[発信者番号ポリシー]** で、割り当てるポリシーを選択し、**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2d82-141">Under **Caller ID policy**, select the policy you want to assign, and then choose **Save**.</span></span>

### <a name="assign-a-custom-calling-line-id-policy-to-multiple-users-at-a-time"></a><span data-ttu-id="e2d82-142">カスタム発信回線 ID ポリシーを複数のユーザーに一度に割り当てる</span><span class="sxs-lookup"><span data-stu-id="e2d82-142">Assign a custom calling line ID policy to multiple users at a time</span></span>

<span data-ttu-id="e2d82-143">一度に複数のユーザーにカスタム発信回線 ID ポリシーを割り当てる方法については、「[一括で Teams のユーザー設定を編集する](edit-user-settings-in-bulk.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2d82-143">To assign a custom calling line Id policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="e2d82-144">または、次の操作も実行できます。</span><span class="sxs-lookup"><span data-stu-id="e2d82-144">Or, you can also do the following:</span></span>

1. <span data-ttu-id="e2d82-145">**[Microsoft Teams 管理センター]** > **[音声]** > **[発信者番号ポリシー]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="e2d82-145">Go to **Microsoft Teams admin center** > **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="e2d82-146">ポリシー名の左側をクリックしてポリシーを選びます。</span><span class="sxs-lookup"><span data-stu-id="e2d82-146">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="e2d82-147">[**ユーザーを管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2d82-147">Select **Manage users**.</span></span>
4. <span data-ttu-id="e2d82-148">[**ユーザーを管理**] ウィンドウで、表示名またはユーザー名でユーザーを検索し、名前を選択して [**追加**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="e2d82-148">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="e2d82-149">追加するユーザーごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="e2d82-149">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="e2d82-150">ユーザーの追加が完了したら、**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2d82-150">When you're finished adding users, select **Save**.</span></span>

### <a name="assign-a-custom-caller-id-policy-to-users-in-a-group"></a><span data-ttu-id="e2d82-151">カスタム発信者番号ポリシーをグループ内のユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="e2d82-151">Assign a custom caller ID policy to users in a group</span></span>

<span data-ttu-id="e2d82-152">あらかじめ特定した複数のユーザーにカスタム ポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="e2d82-152">You may want to assign a custom  policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="e2d82-153">たとえば、セキュリティ グループのすべてのユーザーにポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="e2d82-153">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="e2d82-154">これを行うには、Graph 用 Azure Active Directory PowerShell モジュールと Skype for Business PowerShell モジュールに接続します。</span><span class="sxs-lookup"><span data-stu-id="e2d82-154">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="e2d82-155">PowerShell を使用して Teams を管理する方法の詳細については、「[Teams での PowerShell の概要](teams-powershell-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2d82-155">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="e2d82-156">この例では、「Support Caller ID Policy」という名前のカスタム発信者番号ポリシーを、Contoso サポート グループのすべてのユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="e2d82-156">In this example, we assign a custom caller lID policy called Support Caller ID Policy to all users in the Contoso Support group.</span></span>  

> [!NOTE]
> <span data-ttu-id="e2d82-157">「[単一の Windows PowerShell ウィンドウですべての Office 365 サービスに接続する](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)」の手順に従って、必ず最初に Azure Active Directory PowerShell for Graph モジュールと Skype for Business PowerShell モジュールに接続してください。</span><span class="sxs-lookup"><span data-stu-id="e2d82-157">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="e2d82-158">特定のグループの GroupObjectId を取得します。</span><span class="sxs-lookup"><span data-stu-id="e2d82-158">Get the GroupObjectId of the particular group.</span></span>
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Support"
```
<span data-ttu-id="e2d82-159">指定したグループのメンバーを取得します。</span><span class="sxs-lookup"><span data-stu-id="e2d82-159">Get the members of the specified group.</span></span>
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="e2d82-160">グループ内のすべてのユーザーを特定の発信者番号ポリシーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="e2d82-160">Assign all users in the group to a particular caller ID policy.</span></span> <span data-ttu-id="e2d82-161">この例では、Support Caller ID Policy を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="e2d82-161">In this example, it's Support Caller ID Policy.</span></span>
```PowerShell
$members | ForEach-Object { Grant-CsCallingLineIdentity -PolicyName "Support Caller ID Policy" -Identity $_.UserPrincipalName}
``` 
<span data-ttu-id="e2d82-162">グループ内のメンバー数によっては、このコマンドの実行に数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e2d82-162">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

 ## <a name="related-topics"></a><span data-ttu-id="e2d82-163">関連項目</span><span class="sxs-lookup"><span data-stu-id="e2d82-163">Related topics</span></span>

- [<span data-ttu-id="e2d82-164">New-CsCallingLineIdentity</span><span class="sxs-lookup"><span data-stu-id="e2d82-164">New-CsCallingLineIdentity</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)

