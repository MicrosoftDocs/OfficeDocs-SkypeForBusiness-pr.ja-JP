---
title: Microsoft Teams で発信者番号通知ポリシーを管理する
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
f1keywords: ms.teamsadmincenter.voice.callinglineid.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams で発信者番号ポリシーを使用および管理して、組織内の Teams ユーザーの発信者番号通知を変更またはブロックする方法について説明します。
ms.openlocfilehash: 8a8e235c1adf24e5a11b0b62e7542d5fcae194be
ms.sourcegitcommit: f2c7626dbef4ed250b9a937a9b56d46fe2e2039e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2019
ms.locfileid: "39998825"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a><span data-ttu-id="4d7e2-103">Microsoft Teams で発信者番号通知ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="4d7e2-103">Manage caller ID policies in Microsoft Teams</span></span>

>[!INCLUDE [new-feature-teams-admin-center](includes/new-feature-teams-admin-center.md)]

<span data-ttu-id="4d7e2-104">管理者として、Microsoft Teams の発信者番号ポリシーを使用して、発信者番号を変更またはブロックすることができます (通話回線 ID とも呼ばれます)。</span><span class="sxs-lookup"><span data-stu-id="4d7e2-104">As an admin, you can use caller ID policies in Microsoft Teams to change or block the caller ID (also known as calling line ID).</span></span> <span data-ttu-id="4d7e2-105">既定では、ユーザーが PSTN 携帯電話に通話を発信し、PSTN の発信者の電話番号が Teams ユーザーに発信されたときに、その電話番号が表示されるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="4d7e2-105">By default, the phone number of Teams users can be seen when they make a call to a PSTN phone and the phone number of PSTN callers can be seen when they call a Teams user.</span></span> <span data-ttu-id="4d7e2-106">発信者番号通知ポリシーを使って、組織内の Teams ユーザーに対して別の電話番号を表示したり、着信番号が表示されないようにブロックしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="4d7e2-106">You can use caller ID policies to display an alternate phone number for Teams users in your organization or block an incoming number from being displayed.</span></span>

<span data-ttu-id="4d7e2-107">たとえば、ユーザーが電話をかけるときに、発信者番号認識を変更して、ユーザーの電話番号ではなく、組織の主要な電話番号を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="4d7e2-107">For example, when users make a call, you can change the caller ID to display your organization's main phone number instead of users' phone numbers.</span></span>

<span data-ttu-id="4d7e2-108">発信者番号通知ポリシーを管理するには、Microsoft Teams 管理センターの**音声** > **発信者番号ポリシー**にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="4d7e2-108">You manage caller ID policies by going to **Voice** > **Caller ID policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="4d7e2-109">グローバル (組織全体の既定) ポリシーを使用するか、カスタムポリシーを作成してユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="4d7e2-109">You can use the global (Org-wide default) policy or create custom policies and assign them to users.</span></span> <span data-ttu-id="4d7e2-110">組織内のユーザーは、カスタムポリシーを作成して割り当てる場合を除き、自動的にグローバルポリシーを取得します。</span><span class="sxs-lookup"><span data-stu-id="4d7e2-110">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

<span data-ttu-id="4d7e2-111">グローバルポリシーを編集するか、カスタムポリシーを作成して割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="4d7e2-111">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="4d7e2-112">ユーザーにカスタムポリシーが割り当てられている場合は、そのポリシーがユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="4d7e2-112">If a user is assigned a custom policy, that policy applies to the user.</span></span> <span data-ttu-id="4d7e2-113">ユーザーにカスタムポリシーが割り当てられていない場合は、グローバルポリシーがユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="4d7e2-113">If a user isn't assigned a custom policy, the global policy applies to the user.</span></span>

## <a name="create-a-custom-caller-id-policy"></a><span data-ttu-id="4d7e2-114">カスタム発信者番号ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="4d7e2-114">Create a custom caller ID policy</span></span>

1. <span data-ttu-id="4d7e2-115">Microsoft Teams 管理センターの左のナビゲーションで、[**ボイス** > **発信者番号ポリシー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="4d7e2-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="4d7e2-116">[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4d7e2-116">Click **Add**.</span></span>
<span data-ttu-id="4d7e2-117">![管理センターの新しい発信者番号ポリシーページのスクリーンショット](media/caller-id-policies-add-policy.png)</span><span class="sxs-lookup"><span data-stu-id="4d7e2-117">![Screenshot of new caller ID policy page in the admin center](media/caller-id-policies-add-policy.png)</span></span>
3. <span data-ttu-id="4d7e2-118">ポリシーの名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="4d7e2-118">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="4d7e2-119">ここで、目的の設定を選びます。</span><span class="sxs-lookup"><span data-stu-id="4d7e2-119">From here, choose the settings that you want:</span></span>

    - <span data-ttu-id="4d7e2-120">[着信した発信者番号を**ブロック**]: この設定をオンにすると、着信が表示されないように発信者 id がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="4d7e2-120">**Block incoming caller ID**: Turn on this setting to block the caller ID of incoming calls from being displayed.</span></span>
    - <span data-ttu-id="4d7e2-121">**ユーザーは発信者番号ポリシーを上書きすることができ**ます。この設定を有効にすると、ユーザーがポリシーの設定を上書きして、その番号を呼び出し先に表示するかどうかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="4d7e2-121">**Users can override the caller ID policy**: Turn on this setting to let users override the settings in the policy regarding displaying their number to callees or not.</span></span> <span data-ttu-id="4d7e2-122">これは、ユーザーが発信者番号通知を表示するかどうかを選択できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="4d7e2-122">This means that users can choose whether to display their caller ID.</span></span>
    - <span data-ttu-id="4d7e2-123">[発信者番号の**交換**]: 次のいずれかを選択して、ユーザーに表示される発信者番号を設定します。</span><span class="sxs-lookup"><span data-stu-id="4d7e2-123">**Replace caller ID**: Set the caller ID to be displayed for users by selecting one of the following:</span></span>

        - <span data-ttu-id="4d7e2-124">[**ユーザーの電話番号**: ユーザーの電話番号を表示します。</span><span class="sxs-lookup"><span data-stu-id="4d7e2-124">**User's number**: Displays the user's number.</span></span> 
        - <span data-ttu-id="4d7e2-125">[**サービス番号**: 発信者 ID として表示するサービスの電話番号を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="4d7e2-125">**Service number**: Lets you set a service phone number to display as the caller ID.</span></span>
        - <span data-ttu-id="4d7e2-126">**匿名**: 発信者番号を匿名で表示します。</span><span class="sxs-lookup"><span data-stu-id="4d7e2-126">**Anonymous**: Displays the caller ID as Anonymous.</span></span>

    - <span data-ttu-id="4d7e2-127">**発信者番号認識の代わりに使用するサービス番号**: ユーザーの発信者番号を置き換えるサービス番号を選択します。</span><span class="sxs-lookup"><span data-stu-id="4d7e2-127">**Service number to use to replace the caller ID**: Choose a service number to replace the caller ID of users.</span></span> <span data-ttu-id="4d7e2-128">このオプションは、[発信者番号の**置換**] で [**サービス番号**] を選択した場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="4d7e2-128">This option is available if you selected **Service number** in **Replace caller ID**.</span></span>

5. <span data-ttu-id="4d7e2-129">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4d7e2-129">Click **Save**.</span></span>

## <a name="edit-a-caller-id-policy"></a><span data-ttu-id="4d7e2-130">発信者番号ポリシーを編集する</span><span class="sxs-lookup"><span data-stu-id="4d7e2-130">Edit a caller ID policy</span></span>

<span data-ttu-id="4d7e2-131">グローバルポリシーまたは作成したカスタムポリシーを編集できます。</span><span class="sxs-lookup"><span data-stu-id="4d7e2-131">You can edit the global policy or any custom policies that you create.</span></span> 

1. <span data-ttu-id="4d7e2-132">Microsoft Teams 管理センターの左のナビゲーションで、[**ボイス** > **発信者番号ポリシー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="4d7e2-132">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="4d7e2-133">ポリシー名の左側をクリックしてポリシーを選択し、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4d7e2-133">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="4d7e2-134">必要に応じて設定を変更し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4d7e2-134">Change the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-caller-id-policy-to-users"></a><span data-ttu-id="4d7e2-135">ユーザーにカスタム発信者番号ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="4d7e2-135">Assign a custom caller ID policy to users</span></span>

<span data-ttu-id="4d7e2-136">Microsoft Teams 管理センターを使用して、ユーザー設定のポリシーを1人以上のユーザーまたは Skype for Business PowerShell モジュールに割り当てて、セキュリティグループや配布グループなどのユーザーグループにカスタムポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="4d7e2-136">You can use the Microsoft Teams admin center to assign a custom policy to one or more users or the Skype for Business PowerShell module to assign a custom policy to groups of users, such as a security group or distribution group.</span></span>

### <a name="assign-a-custom-caller-line-id-policy-to-a-user"></a><span data-ttu-id="4d7e2-137">カスタム発信者番号通知ポリシーをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="4d7e2-137">Assign a custom caller line ID policy to a user</span></span>

1. <span data-ttu-id="4d7e2-138">Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動してユーザーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="4d7e2-138">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="4d7e2-139">[**ポリシー**] をクリックし、[**割り当てられたポリシー**] の横にある [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4d7e2-139">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="4d7e2-140">[**発信者番号ポリシー**] で、割り当てるポリシーを選び、[**保存**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="4d7e2-140">Under **Caller ID policy**, select the policy you want to assign, and then choose **Save**.</span></span>

### <a name="assign-a-custom-calling-line-id-policy-to-multiple-users-at-a-time"></a><span data-ttu-id="4d7e2-141">ユーザー設定の発信行 ID ポリシーを一度に複数のユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="4d7e2-141">Assign a custom calling line ID policy to multiple users at a time</span></span>

<span data-ttu-id="4d7e2-142">ユーザー設定の発信行 Id ポリシーを一度に複数のユーザーに割り当てるには、「 [Teams のユーザー設定を一括](edit-user-settings-in-bulk.md)して編集する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4d7e2-142">To assign a custom calling line Id policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="4d7e2-143">または、次の操作も行うことができます。</span><span class="sxs-lookup"><span data-stu-id="4d7e2-143">Or, you can also do the following:</span></span>

1. <span data-ttu-id="4d7e2-144">**Microsoft Teams 管理センター** > の**ボイス** > **発信者番号のポリシー**に移動します。</span><span class="sxs-lookup"><span data-stu-id="4d7e2-144">Go to **Microsoft Teams admin center** > **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="4d7e2-145">ポリシー名の左側をクリックして、ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="4d7e2-145">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="4d7e2-146">[**ユーザーの管理**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="4d7e2-146">Select **Manage users**.</span></span>
4. <span data-ttu-id="4d7e2-147">[**ユーザーの管理**] ウィンドウで、[表示名] または [ユーザー名] でユーザーを検索し、名前を選択して [**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4d7e2-147">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="4d7e2-148">追加するユーザーごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="4d7e2-148">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="4d7e2-149">ユーザーの追加が完了したら、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4d7e2-149">When you're finished adding users, select **Save**.</span></span>

### <a name="assign-a-custom-caller-id-policy-to-users-in-a-group"></a><span data-ttu-id="4d7e2-150">ユーザー設定の発信者番号ポリシーをグループ内のユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="4d7e2-150">Assign a custom caller ID policy to users in a group</span></span>

<span data-ttu-id="4d7e2-151">既に識別した複数のユーザーにカスタムポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="4d7e2-151">You may want to assign a custom  policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="4d7e2-152">たとえば、セキュリティグループ内のすべてのユーザーにポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="4d7e2-152">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="4d7e2-153">これを行うには、Azure Active Directory PowerShell for Graph モジュールと Skype for Business PowerShell モジュールに接続します。</span><span class="sxs-lookup"><span data-stu-id="4d7e2-153">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="4d7e2-154">PowerShell を使用して Teams を管理する方法の詳細については、「[Teams での PowerShell の概要](teams-powershell-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4d7e2-154">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="4d7e2-155">この例では、Contoso サポートグループ内のすべてのユーザーに発信者番号通知をサポートするカスタムの発信者番号ポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="4d7e2-155">In this example, we assign a custom caller lID policy called Support Caller ID Policy to all users in the Contoso Support group.</span></span>  

> [!NOTE]
> <span data-ttu-id="4d7e2-156">「[単一の Windows PowerShell ウィンドウですべての Office 365 サービスに接続する](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)」の手順に従って、必ず最初に Azure Active Directory PowerShell for Graph モジュールと Skype for Business PowerShell モジュールに接続してください。</span><span class="sxs-lookup"><span data-stu-id="4d7e2-156">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="4d7e2-157">特定のグループの GroupObjectId を取得します。</span><span class="sxs-lookup"><span data-stu-id="4d7e2-157">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso Support"
```
<span data-ttu-id="4d7e2-158">指定したグループのメンバーを取得します。</span><span class="sxs-lookup"><span data-stu-id="4d7e2-158">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="4d7e2-159">グループ内のすべてのユーザーを特定の発信者番号ポリシーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="4d7e2-159">Assign all users in the group to a particular caller ID policy.</span></span> <span data-ttu-id="4d7e2-160">この例では、発信者番号ポリシーがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="4d7e2-160">In this example, it's Support Caller ID Policy.</span></span>
```
$members | ForEach-Object { Grant-CsCallingLineIdentity -PolicyName "Support Caller ID Policy" -Identity $_.UserPrincipalName}
``` 
<span data-ttu-id="4d7e2-161">グループ内のメンバー数によっては、このコマンドの実行に数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="4d7e2-161">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

 ## <a name="related-topics"></a><span data-ttu-id="4d7e2-162">関連項目</span><span class="sxs-lookup"><span data-stu-id="4d7e2-162">Related topics</span></span>

- [<span data-ttu-id="4d7e2-163">新規-CsCallingLineIdentity</span><span class="sxs-lookup"><span data-stu-id="4d7e2-163">New-CsCallingLineIdentity</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)

