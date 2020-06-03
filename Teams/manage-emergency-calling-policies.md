---
title: Microsoft Teams で緊急通話ポリシーを管理する
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords: ms.teamsadmincenter.voice.emergencycallingpolicies.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams で緊急通話ポリシーを使用して管理する方法について説明します。この方法では、組織内の Teams ユーザーが緊急通報を行ったときの動作を定義します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 98d6fb5eba98701cddccb808e5670fb34a00efbf
ms.sourcegitcommit: d8e05e66311725f8ff6d28011355129baeb305b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/03/2020
ms.locfileid: "44539484"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a><span data-ttu-id="2c104-103">Microsoft Teams で緊急通話ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="2c104-103">Manage emergency calling policies in Microsoft Teams</span></span>

<span data-ttu-id="2c104-104">組織で[通話プラン](set-up-calling-plans.md)を使用している場合、または[電話システムダイレクトルーティング](direct-routing-landing-page.md)を展開している場合は、Microsoft teams の緊急通話ポリシーを使用して、組織内の Teams ユーザーが緊急通報を行ったときの動作を定義できます。</span><span class="sxs-lookup"><span data-stu-id="2c104-104">If your organization uses [Calling Plans](set-up-calling-plans.md) or deployed [Phone System Direct Routing](direct-routing-landing-page.md), you can use emergency calling policies in Microsoft Teams to define what happens when a Teams user in your organization makes an emergency call.</span></span> <span data-ttu-id="2c104-105">ポリシーを割り当てられたユーザーが緊急サービスを呼び出すときの通知方法と通知方法を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="2c104-105">You can set who to notify and how they are notified when a user who is assigned the policy calls emergency services.</span></span> <span data-ttu-id="2c104-106">たとえば、ポリシー設定を構成して、組織のセキュリティデスクに自動的に通知し、緊急通話で聞くことができます。</span><span class="sxs-lookup"><span data-stu-id="2c104-106">For example, you can configure policy settings to automatically notify your organization's security desk and have them listen in emergency calls.</span></span>  

<span data-ttu-id="2c104-107">緊急通話のポリシーを管理するに**Voice**  >  は、Microsoft Teams 管理センターのボイス**緊急ポリシー**または Windows PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="2c104-107">You manage emergency calling policies by going to **Voice** > **Emergency policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span> <span data-ttu-id="2c104-108">ポリシーは、ユーザーと[ネットワークサイト](cloud-voice-network-settings.md)に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="2c104-108">The policies can be assigned to users and [network sites](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="2c104-109">ユーザーの場合は、グローバル (組織全体の既定) ポリシーを使用するか、カスタムポリシーを作成して割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="2c104-109">For users, you can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="2c104-110">カスタムポリシーを作成して割り当てる場合を除き、ユーザーはグローバルポリシーを自動的に取得します。</span><span class="sxs-lookup"><span data-stu-id="2c104-110">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="2c104-111">グローバルポリシーの設定は編集できますが、名前の変更や削除はできないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="2c104-111">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span> <span data-ttu-id="2c104-112">ネットワークサイトの場合は、カスタムポリシーを作成して割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c104-112">For network sites, you create and assign custom policies.</span></span>

<span data-ttu-id="2c104-113">緊急通話のポリシーをネットワークサイトとユーザーに割り当てている場合、そのユーザーがそのネットワークサイトを使用している場合は、そのネットワークサイトに割り当てられているポリシーが、ユーザーに割り当てられているポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="2c104-113">If you assigned an emergency calling policy to a network site and to a user and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="create-a-custom-emergency-calling-policy"></a><span data-ttu-id="2c104-114">ユーザー設定の緊急通話ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="2c104-114">Create a custom emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="2c104-115">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="2c104-115">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="2c104-116">Microsoft Teams 管理センターの左のナビゲーションで、[**ボイス**  >  **緊急ポリシー**] に移動し、[**通話ポリシー** ] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="2c104-116">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="2c104-117">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2c104-117">Click **Add**.</span></span>
3. <span data-ttu-id="2c104-118">ポリシーの名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="2c104-118">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="2c104-119">緊急通報が行われたときに、組織内のユーザーに通知する方法 (通常はセキュリティデスク) を設定します。</span><span class="sxs-lookup"><span data-stu-id="2c104-119">Set how you want to notify people in your organization, typically the security desk, when an emergency call is made.</span></span> <span data-ttu-id="2c104-120">これを行うには、[**通知モード**] で、次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="2c104-120">To do this, under **Notification mode**, select one of the following:</span></span>
    - <span data-ttu-id="2c104-121">**通知のみ送信**: チームチャットメッセージは、指定したユーザーとグループに送信されます。</span><span class="sxs-lookup"><span data-stu-id="2c104-121">**Send notification only**: A Teams chat message is sent to the users and groups that you specify.</span></span>
    - <span data-ttu-id="2c104-122">**Conferenced がミュートになっている**場合: チームチャットメッセージは、指定したユーザーとグループに送信され、発信者と psap 演算子の間の会話に参加することはできますが、参加することはできません。</span><span class="sxs-lookup"><span data-stu-id="2c104-122">**Conferenced in but are muted**: A Teams chat message is sent to the users and groups that you specify and they can listen (but not participate) in the conversation between the caller and the PSAP operator.</span></span>
    - <span data-ttu-id="2c104-123">**Conferenced in and is ミュート** **(近**日公開): チームチャットメッセージは指定したユーザーとグループに送信され、ミュートを解除して、発信者と psap 演算子の間の会話に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="2c104-123">**Conferenced in and are unmuted** **(coming soon)**: A Teams chat message is sent to the users and groups that you specify and they can unmute to listen and participate in the conversation between the caller and the PSAP operator.</span></span>
5.  <span data-ttu-id="2c104-124">Conferenced を選択した**が**、[**緊急通話にダイヤルする番号**] がオンになっている場合は、ユーザーまたはグループの PSTN 電話番号を入力して、通話を発信し、緊急通話に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="2c104-124">If you selected the **Conferenced in but are muted** notification mode, in the **Numbers to dial for emergency calls notifications** box, you can enter a PSTN phone number of a user or group to call and join the emergency call.</span></span> <span data-ttu-id="2c104-125">たとえば、組織のセキュリティデスクの番号を入力すると、緊急通話の発信時に通話を受けられ、通話を聞くことができます。</span><span class="sxs-lookup"><span data-stu-id="2c104-125">For example, enter the number of your organization's security desk, who will receive a call when an emergency call is made and can then listen in on the call.</span></span>
6. <span data-ttu-id="2c104-126">緊急通報が行われたときに通知するために、1人以上のユーザーまたはグループ (組織のセキュリティデスクなど) を検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="2c104-126">Search for and select one or more users or groups, such as your organization's security desk, to notify when an emergency call is made.</span></span>  <span data-ttu-id="2c104-127">通知は、ユーザー、配布グループ、セキュリティグループのメールアドレスに送信できます。</span><span class="sxs-lookup"><span data-stu-id="2c104-127">The notification can be sent to email addresses of users, distribution groups, and security groups.</span></span> <span data-ttu-id="2c104-128">通知できるユーザーの最大数は50です。</span><span class="sxs-lookup"><span data-stu-id="2c104-128">A maximum of 50 users can be notified.</span></span>
7. <span data-ttu-id="2c104-129">[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2c104-129">Click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="2c104-130">PowerShell を使用する場合</span><span class="sxs-lookup"><span data-stu-id="2c104-130">Using PowerShell</span></span>

<span data-ttu-id="2c104-131">「[新規-CsTeamsEmergencyCallingPolicy」を](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy)参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c104-131">See [New-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy).</span></span>

## <a name="edit-an-emergency-calling-policy"></a><span data-ttu-id="2c104-132">緊急通話のポリシーを編集する</span><span class="sxs-lookup"><span data-stu-id="2c104-132">Edit an emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="2c104-133">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="2c104-133">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="2c104-134">グローバル ポリシー、または作成したカスタム ポリシーを編集できます。</span><span class="sxs-lookup"><span data-stu-id="2c104-134">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="2c104-135">Microsoft Teams 管理センターの左のナビゲーションで、[**ボイス**  >  **緊急ポリシー**] に移動し、[**通話ポリシー** ] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="2c104-135">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="2c104-136">ポリシー名の左側をクリックしてポリシーを選び、**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2c104-136">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="2c104-137">必要な変更を加えて、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2c104-137">Make the changes that you want, and then click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="2c104-138">PowerShell を使用する場合</span><span class="sxs-lookup"><span data-stu-id="2c104-138">Using PowerShell</span></span>

<span data-ttu-id="2c104-139">「 [Set-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c104-139">See [Set-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy).</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a><span data-ttu-id="2c104-140">ユーザーにカスタム緊急通話ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="2c104-140">Assign a custom emergency calling policy to users</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="2c104-141">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="2c104-141">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="2c104-142">1人のユーザーにポリシーを割り当てるには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="2c104-142">To assign a policy to one user:</span></span>

1. <span data-ttu-id="2c104-143">Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動してユーザーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="2c104-143">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="2c104-144">**[ポリシー]** をクリックし、**[割り当てられたポリシー]** の横にある **[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2c104-144">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="2c104-145">[**緊急通話ポリシー**] で、割り当てるポリシーを選択し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2c104-145">Under **Emergency calling policy**, select the policy you want to assign, and then click **Save**.</span></span>

<span data-ttu-id="2c104-146">複数のユーザーに同時にポリシーを割り当てるには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="2c104-146">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="2c104-147">Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動し、ユーザーを検索するか、表示にフィルターを適用してユーザーを表示します。</span><span class="sxs-lookup"><span data-stu-id="2c104-147">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="2c104-148">[**&#x2713;** (チェックマーク)] の列からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="2c104-148">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="2c104-149">すべてのユーザーを選択するには、表の上部にある [&#x2713; (チェックマーク)] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2c104-149">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="2c104-150">[**設定の編集**] をクリックし、必要な変更を行い、[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2c104-150">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>  

<span data-ttu-id="2c104-151">または、次の操作も実行できます。</span><span class="sxs-lookup"><span data-stu-id="2c104-151">Or, you can also do the following:</span></span>

1. <span data-ttu-id="2c104-152">Microsoft Teams 管理センターの左のナビゲーションで、[**ボイス**  >  **緊急ポリシー**] に移動し、[**通話ポリシー** ] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="2c104-152">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="2c104-153">ポリシー名の左側をクリックしてポリシーを選びます。</span><span class="sxs-lookup"><span data-stu-id="2c104-153">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="2c104-154">[**ユーザーを管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2c104-154">Select **Manage users**.</span></span>
4. <span data-ttu-id="2c104-155">[**ユーザーを管理**] ウィンドウで、表示名またはユーザー名でユーザーを検索し、名前を選択して [**追加**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="2c104-155">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="2c104-156">追加するユーザーごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="2c104-156">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="2c104-157">ユーザーの追加が完了したら、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2c104-157">When you're finished adding users, click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="2c104-158">PowerShell を使用する場合</span><span class="sxs-lookup"><span data-stu-id="2c104-158">Using PowerShell</span></span>

#### <a name="assign-a-custom-emergency-calling-policy-to-a-user"></a><span data-ttu-id="2c104-159">ユーザーにカスタム緊急通話ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="2c104-159">Assign a custom emergency calling policy to a user</span></span>

<span data-ttu-id="2c104-160">「 [Grant-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c104-160">See [Grant-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy).</span></span>

#### <a name="assign-a-custom-emergency-calling-policy-to-users-in-a-group"></a><span data-ttu-id="2c104-161">ユーザー設定の緊急通話ポリシーをグループ内のユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="2c104-161">Assign a custom emergency calling policy to users in a group</span></span>

<span data-ttu-id="2c104-162">複数のユーザーに対して、既に特定した緊急通話のポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="2c104-162">You may want to assign a custom emergency calling policy to multiple users that you've already identified.</span></span> <span data-ttu-id="2c104-163">たとえば、セキュリティ グループのすべてのユーザーにポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="2c104-163">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="2c104-164">これを行うには、Graph 用 Azure Active Directory PowerShell モジュールと Skype for Business PowerShell モジュールに接続します。</span><span class="sxs-lookup"><span data-stu-id="2c104-164">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span>

<span data-ttu-id="2c104-165">この例では、[Contoso の運営] グループのすべてのユーザーに、[操作緊急通話] ポリシーと呼ばれるポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="2c104-165">In this example, we assign a policy called Operations Emergency Calling Policy to all users in the Contoso Operations group.</span></span>  

> [!NOTE]
> <span data-ttu-id="2c104-166">「[単一の Windows PowerShell ウィンドウですべての Office 365 サービスに接続する](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)」の手順に従って、必ず最初に Azure Active Directory PowerShell for Graph モジュールと Skype for Business PowerShell モジュールに接続してください。</span><span class="sxs-lookup"><span data-stu-id="2c104-166">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="2c104-167">特定のグループの GroupObjectId を取得します。</span><span class="sxs-lookup"><span data-stu-id="2c104-167">Get the GroupObjectId of the particular group.</span></span>
```powershell
$group = Get-AzureADGroup -SearchString "Contoso Operations"
```
<span data-ttu-id="2c104-168">指定したグループのメンバーを取得します。</span><span class="sxs-lookup"><span data-stu-id="2c104-168">Get the members of the specified group.</span></span>
```powershell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="2c104-169">グループ内のすべてのユーザーを特定のチーム ポリシーに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="2c104-169">Assign all users in the group to a particular teams policy.</span></span> <span data-ttu-id="2c104-170">この例では、操作は緊急通話ルーティングポリシーです。</span><span class="sxs-lookup"><span data-stu-id="2c104-170">In this example, it's Operations Emergency Call Routing Policy.</span></span>
```powershell
$members | ForEach-Object {Grant-CsTeamsEmergencyCallingPolicy -PolicyName "Operations Emergency Calling Policy" -Identity $_.UserPrincipalName}
``` 
<span data-ttu-id="2c104-171">グループ内のメンバー数によっては、このコマンドの実行に数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="2c104-171">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a><span data-ttu-id="2c104-172">ユーザー設定の緊急通話ポリシーをネットワークサイトに割り当てる</span><span class="sxs-lookup"><span data-stu-id="2c104-172">Assign a custom emergency calling policy to a network site</span></span>

<span data-ttu-id="2c104-173">[CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite)コマンドレットを使用して、緊急通話ポリシーをネットワークサイトに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="2c104-173">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) cmdlet to assign an emergency calling policy to a network site.</span></span>

<span data-ttu-id="2c104-174">次の例は、Contoso 緊急通話ポリシー1と呼ばれるポリシーを Site1 サイトに割り当てる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="2c104-174">The following example shows how to assign a policy called Contoso Emergency Calling Policy 1 to the Site1 site.</span></span>

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a><span data-ttu-id="2c104-175">関連項目</span><span class="sxs-lookup"><span data-stu-id="2c104-175">Related topics</span></span>

- [<span data-ttu-id="2c104-176">Teams で緊急通話ルーティングポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="2c104-176">Manage emergency call routing policies in Teams</span></span>](manage-emergency-call-routing-policies.md)
- [<span data-ttu-id="2c104-177">Teams での PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="2c104-177">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="2c104-178">チームのユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="2c104-178">Assign policies to your users in Teams</span></span>](assign-policies.md)
