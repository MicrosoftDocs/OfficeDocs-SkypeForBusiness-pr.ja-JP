---
title: 緊急通話ポリシーを管理Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams で緊急通話ポリシーを使用および管理して、組織内の Teams ユーザーが緊急通話を行った場合の対応を定義する方法について説明します。
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallingpolicies.overview
ms.openlocfilehash: 34f6e901049dd080ee070e7858f24b70535ee189
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120568"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a><span data-ttu-id="17d51-103">緊急通話ポリシーを管理Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="17d51-103">Manage emergency calling policies in Microsoft Teams</span></span>

<span data-ttu-id="17d51-104">組織で通話プラン[](set-up-calling-plans.md)を使用している場合、または[電話システム](direct-routing-landing-page.md)ダイレクト ルーティング を展開している場合は、Microsoft Teams の緊急通話ポリシーを使用して、組織内の Teams ユーザーが緊急通話を行った場合の処理を定義できます。</span><span class="sxs-lookup"><span data-stu-id="17d51-104">If your organization uses [Calling Plans](set-up-calling-plans.md) or deployed [Phone System Direct Routing](direct-routing-landing-page.md), you can use emergency calling policies in Microsoft Teams to define what happens when a Teams user in your organization makes an emergency call.</span></span> <span data-ttu-id="17d51-105">ポリシーが割り当てられているユーザーが緊急サービスを呼び出したときに通知するユーザーと通知方法を設定できます。</span><span class="sxs-lookup"><span data-stu-id="17d51-105">You can set who to notify and how they are notified when a user who is assigned the policy calls emergency services.</span></span> <span data-ttu-id="17d51-106">たとえば、ポリシー設定を構成して、組織のセキュリティ デスクに自動的に通知し、緊急通話でリッスンすることができます。</span><span class="sxs-lookup"><span data-stu-id="17d51-106">For example, you can configure policy settings to automatically notify your organization's security desk and have them listen in emergency calls.</span></span>  

<span data-ttu-id="17d51-107">緊急通話ポリシーを管理するには、Microsoft Teams管理センターで音声緊急ポリシーに移動するか  >  、Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="17d51-107">You manage emergency calling policies by going to **Voice** > **Emergency policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span> <span data-ttu-id="17d51-108">ポリシーは、ユーザーとネットワーク サイトに [割り当てることができます](cloud-voice-network-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="17d51-108">The policies can be assigned to users and [network sites](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="17d51-109">ユーザーの場合は、グローバル (組織全体の既定) ポリシーを使用するか、カスタム ポリシーを作成して割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="17d51-109">For users, you can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="17d51-110">カスタム ポリシーを作成して割り当てない限り、ユーザーは自動的にグローバル ポリシーを取得します。</span><span class="sxs-lookup"><span data-stu-id="17d51-110">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="17d51-111">グローバル ポリシーの設定は編集できますが、名前の変更や削除はできないので、ご安心ください。</span><span class="sxs-lookup"><span data-stu-id="17d51-111">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span> <span data-ttu-id="17d51-112">ネットワーク サイトの場合は、カスタム ポリシーを作成して割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="17d51-112">For network sites, you create and assign custom policies.</span></span>

<span data-ttu-id="17d51-113">緊急通話ポリシーをネットワーク サイトとユーザーに割り当て、そのユーザーがネットワーク サイトにある場合、ネットワーク サイトに割り当てられているポリシーは、ユーザーに割り当てられているポリシーを上書きします。</span><span class="sxs-lookup"><span data-stu-id="17d51-113">If you assigned an emergency calling policy to a network site and to a user and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="create-a-custom-emergency-calling-policy"></a><span data-ttu-id="17d51-114">カスタム緊急通話ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="17d51-114">Create a custom emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="17d51-115">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="17d51-115">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="17d51-116">管理センターの左側のナビゲーションMicrosoft Teams、[**音声緊急対応** ポリシー] に移動し、[通話ポリシー] タブ  >  **をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="17d51-116">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="17d51-117">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17d51-117">Click **Add**.</span></span>
3. <span data-ttu-id="17d51-118">ポリシーの名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="17d51-118">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="17d51-119">緊急通話が行われたときに組織内のユーザー (通常はセキュリティ デスク) に通知する方法を設定します。</span><span class="sxs-lookup"><span data-stu-id="17d51-119">Set how you want to notify people in your organization, typically the security desk, when an emergency call is made.</span></span> <span data-ttu-id="17d51-120">これを行うには、[通知モード **] で**、次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="17d51-120">To do this, under **Notification mode**, select one of the following:</span></span>
    - <span data-ttu-id="17d51-121">**通知のみを送信** する: Teamsメッセージが、指定したユーザーとグループに送信されます。</span><span class="sxs-lookup"><span data-stu-id="17d51-121">**Send notification only**: A Teams chat message is sent to the users and groups that you specify.</span></span>
    - <span data-ttu-id="17d51-122">**ミュート** 状態で電話会議を行い、ミュートを解除できない: Teams チャット メッセージが、指定したユーザーとグループに送信され、発信者と PSAP オペレーターの間の会話でリッスン (参加できません) できます。</span><span class="sxs-lookup"><span data-stu-id="17d51-122">**Conferenced in muted and unable to unmute**: A Teams chat message is sent to the users and groups that you specify and they can listen (but not participate) in the conversation between the caller and the PSAP operator.</span></span>
    - <span data-ttu-id="17d51-123">**ミュート** で電話会議を行うがミュート解除可能: Teams チャット メッセージは、指定したユーザーとグループに送信され、発信者と PSAP オペレーターの間の会話を聞いて参加するためにミュートを解除できます。</span><span class="sxs-lookup"><span data-stu-id="17d51-123">**Conferenced in muted but are able to unmute**: A Teams chat message is sent to the users and groups that you specify and they can unmute to listen and participate in the conversation between the caller and the PSAP operator.</span></span>
5.  <span data-ttu-id="17d51-124">いずれかの会議をミュート通知モードで選択した場合は、[緊急通話の通知をダイヤルする番号] ボックスに、緊急通話を発信して参加するユーザーまたはグループの PSTN 電話番号を入力できます。</span><span class="sxs-lookup"><span data-stu-id="17d51-124">If you selected either of the **Conference in muted** notification modes, in the **Numbers to dial for emergency calls notifications** box, you can enter a PSTN phone number of a user or group to call and join the emergency call.</span></span> <span data-ttu-id="17d51-125">たとえば、組織のセキュリティ デスクの番号を入力します。緊急通話が行われたときに通話を受け取り、その後、通話をリッスンできます。</span><span class="sxs-lookup"><span data-stu-id="17d51-125">For example, enter the number of your organization's security desk, who will receive a call when an emergency call is made and can then listen in on the call.</span></span> <span data-ttu-id="17d51-126">モードが [電話会議] にミュートに設定されているが、ミュートを解除できる場合でも、PSTN 電話を **ミュート解除することはできません**。</span><span class="sxs-lookup"><span data-stu-id="17d51-126">The PSTN phone cannot be unmuted even when the mode is set to **Conferenced in muted but are able to unmute**.</span></span>
6. <span data-ttu-id="17d51-127">緊急通話が行われたときに通知する 1 つ以上のユーザーまたはグループ (組織のセキュリティ デスクなど) を検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="17d51-127">Search for and select one or more users or groups, such as your organization's security desk, to notify when an emergency call is made.</span></span>  <span data-ttu-id="17d51-128">通知は、ユーザー、配布グループ、およびセキュリティ グループのメール アドレスに送信できます。</span><span class="sxs-lookup"><span data-stu-id="17d51-128">The notification can be sent to email addresses of users, distribution groups, and security groups.</span></span> <span data-ttu-id="17d51-129">最大 50 人のユーザーに通知できます。</span><span class="sxs-lookup"><span data-stu-id="17d51-129">A maximum of 50 users can be notified.</span></span>
7. <span data-ttu-id="17d51-130">[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17d51-130">Click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="17d51-131">PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="17d51-131">Using PowerShell</span></span>

<span data-ttu-id="17d51-132">[New-CsTeamsEmergencyCallingPolicy を参照してください](/powershell/module/skype/new-csteamsemergencycallingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="17d51-132">See [New-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/new-csteamsemergencycallingpolicy).</span></span>

## <a name="edit-an-emergency-calling-policy"></a><span data-ttu-id="17d51-133">緊急通話ポリシーを編集する</span><span class="sxs-lookup"><span data-stu-id="17d51-133">Edit an emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="17d51-134">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="17d51-134">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="17d51-135">グローバル ポリシー、または作成したカスタム ポリシーを編集できます。</span><span class="sxs-lookup"><span data-stu-id="17d51-135">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="17d51-136">管理センターの左側のナビゲーションMicrosoft Teams、[**音声緊急対応** ポリシー] に移動し、[通話ポリシー] タブ  >  **をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="17d51-136">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="17d51-137">ポリシー名の左側をクリックしてポリシーを選び、**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17d51-137">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="17d51-138">必要な変更を行い、[適用] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="17d51-138">Make the changes that you want, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="17d51-139">PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="17d51-139">Using PowerShell</span></span>

<span data-ttu-id="17d51-140">[「Set-CsTeamsEmergencyCallingPolicy」を参照してください](/powershell/module/skype/set-csteamsemergencycallingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="17d51-140">See [Set-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/set-csteamsemergencycallingpolicy).</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a><span data-ttu-id="17d51-141">カスタム緊急通話ポリシーをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="17d51-141">Assign a custom emergency calling policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="17d51-142">[Grant-CsTeamsEmergencyCallingPolicy も参照してください](/powershell/module/skype/grant-csteamsemergencycallingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="17d51-142">See also [Grant-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/grant-csteamsemergencycallingpolicy).</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a><span data-ttu-id="17d51-143">ネットワーク サイトにカスタム緊急通話ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="17d51-143">Assign a custom emergency calling policy to a network site</span></span>

<span data-ttu-id="17d51-144">[Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite)コマンドレットを使用して、緊急通話ポリシーをネットワーク サイトに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="17d51-144">Use the [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) cmdlet to assign an emergency calling policy to a network site.</span></span>

<span data-ttu-id="17d51-145">次の例は、Contoso 緊急通話ポリシー 1 というポリシーを Site1 サイトに割り当てる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="17d51-145">The following example shows how to assign a policy called Contoso Emergency Calling Policy 1 to the Site1 site.</span></span>

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a><span data-ttu-id="17d51-146">関連トピック</span><span class="sxs-lookup"><span data-stu-id="17d51-146">Related topics</span></span>

[<span data-ttu-id="17d51-147">緊急通話ルーティング ポリシーを管理Teams</span><span class="sxs-lookup"><span data-stu-id="17d51-147">Manage emergency call routing policies in Teams</span></span>](manage-emergency-call-routing-policies.md)

[<span data-ttu-id="17d51-148">Teams での PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="17d51-148">Teams PowerShell overview</span></span>](teams-powershell-overview.md)

[<span data-ttu-id="17d51-149"> Teams でユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="17d51-149">Assign policies to your users in Teams</span></span>](assign-policies.md)