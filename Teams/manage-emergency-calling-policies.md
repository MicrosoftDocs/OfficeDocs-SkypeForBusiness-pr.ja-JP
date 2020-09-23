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
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams で緊急通話ポリシーを使用して管理する方法について説明します。この方法では、組織内の Teams ユーザーが緊急通報を行ったときの動作を定義します。
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallingpolicies.overview
ms.openlocfilehash: ac2c06e9ba93e650909ee776383f1cebd9da1a9d
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217668"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a><span data-ttu-id="be1a6-103">Microsoft Teams で緊急通話ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="be1a6-103">Manage emergency calling policies in Microsoft Teams</span></span>

<span data-ttu-id="be1a6-104">組織で [通話プラン](set-up-calling-plans.md) を使用している場合、または [電話システムダイレクトルーティング](direct-routing-landing-page.md)を展開している場合は、Microsoft teams の緊急通話ポリシーを使用して、組織内の Teams ユーザーが緊急通報を行ったときの動作を定義できます。</span><span class="sxs-lookup"><span data-stu-id="be1a6-104">If your organization uses [Calling Plans](set-up-calling-plans.md) or deployed [Phone System Direct Routing](direct-routing-landing-page.md), you can use emergency calling policies in Microsoft Teams to define what happens when a Teams user in your organization makes an emergency call.</span></span> <span data-ttu-id="be1a6-105">ポリシーを割り当てられたユーザーが緊急サービスを呼び出すときの通知方法と通知方法を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="be1a6-105">You can set who to notify and how they are notified when a user who is assigned the policy calls emergency services.</span></span> <span data-ttu-id="be1a6-106">たとえば、ポリシー設定を構成して、組織のセキュリティデスクに自動的に通知し、緊急通話で聞くことができます。</span><span class="sxs-lookup"><span data-stu-id="be1a6-106">For example, you can configure policy settings to automatically notify your organization's security desk and have them listen in emergency calls.</span></span>  

<span data-ttu-id="be1a6-107">緊急通話のポリシーを管理するに**Voice**  >  は、Microsoft Teams 管理センターのボイス**緊急ポリシー**または Windows PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="be1a6-107">You manage emergency calling policies by going to **Voice** > **Emergency policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span> <span data-ttu-id="be1a6-108">ポリシーは、ユーザーと [ネットワークサイト](cloud-voice-network-settings.md)に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="be1a6-108">The policies can be assigned to users and [network sites](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="be1a6-109">ユーザーの場合は、グローバル (組織全体の既定) ポリシーを使用するか、カスタムポリシーを作成して割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="be1a6-109">For users, you can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="be1a6-110">カスタムポリシーを作成して割り当てる場合を除き、ユーザーはグローバルポリシーを自動的に取得します。</span><span class="sxs-lookup"><span data-stu-id="be1a6-110">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="be1a6-111">グローバルポリシーの設定は編集できますが、名前の変更や削除はできないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="be1a6-111">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span> <span data-ttu-id="be1a6-112">ネットワークサイトの場合は、カスタムポリシーを作成して割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="be1a6-112">For network sites, you create and assign custom policies.</span></span>

<span data-ttu-id="be1a6-113">緊急通話のポリシーをネットワークサイトとユーザーに割り当てている場合、そのユーザーがそのネットワークサイトを使用している場合は、そのネットワークサイトに割り当てられているポリシーが、ユーザーに割り当てられているポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="be1a6-113">If you assigned an emergency calling policy to a network site and to a user and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="create-a-custom-emergency-calling-policy"></a><span data-ttu-id="be1a6-114">ユーザー設定の緊急通話ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="be1a6-114">Create a custom emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="be1a6-115">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="be1a6-115">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="be1a6-116">Microsoft Teams 管理センターの左のナビゲーションで、[**ボイス**  >  **緊急ポリシー**] に移動し、[**通話ポリシー** ] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="be1a6-116">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="be1a6-117">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="be1a6-117">Click **Add**.</span></span>
3. <span data-ttu-id="be1a6-118">ポリシーの名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="be1a6-118">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="be1a6-119">緊急通報が行われたときに、組織内のユーザーに通知する方法 (通常はセキュリティデスク) を設定します。</span><span class="sxs-lookup"><span data-stu-id="be1a6-119">Set how you want to notify people in your organization, typically the security desk, when an emergency call is made.</span></span> <span data-ttu-id="be1a6-120">これを行うには、[ **通知モード**] で、次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="be1a6-120">To do this, under **Notification mode**, select one of the following:</span></span>
    - <span data-ttu-id="be1a6-121">**通知のみ送信**: チームチャットメッセージは、指定したユーザーとグループに送信されます。</span><span class="sxs-lookup"><span data-stu-id="be1a6-121">**Send notification only**: A Teams chat message is sent to the users and groups that you specify.</span></span>
    - <span data-ttu-id="be1a6-122">**Conferenced がミュートになっている**場合: チームチャットメッセージは、指定したユーザーとグループに送信され、発信者と psap 演算子の間の会話に参加することはできますが、参加することはできません。</span><span class="sxs-lookup"><span data-stu-id="be1a6-122">**Conferenced in but are muted**: A Teams chat message is sent to the users and groups that you specify and they can listen (but not participate) in the conversation between the caller and the PSAP operator.</span></span>
    - <span data-ttu-id="be1a6-123">**Conferenced in and is ミュート** **(近**日公開): チームチャットメッセージは指定したユーザーとグループに送信され、ミュートを解除して、発信者と psap 演算子の間の会話に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="be1a6-123">**Conferenced in and are unmuted** **(coming soon)**: A Teams chat message is sent to the users and groups that you specify and they can unmute to listen and participate in the conversation between the caller and the PSAP operator.</span></span>
5.  <span data-ttu-id="be1a6-124">Conferenced を選択した **が** 、[ **緊急通話にダイヤルする番号** ] がオンになっている場合は、ユーザーまたはグループの PSTN 電話番号を入力して、通話を発信し、緊急通話に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="be1a6-124">If you selected the **Conferenced in but are muted** notification mode, in the **Numbers to dial for emergency calls notifications** box, you can enter a PSTN phone number of a user or group to call and join the emergency call.</span></span> <span data-ttu-id="be1a6-125">たとえば、組織のセキュリティデスクの番号を入力すると、緊急通話の発信時に通話を受けられ、通話を聞くことができます。</span><span class="sxs-lookup"><span data-stu-id="be1a6-125">For example, enter the number of your organization's security desk, who will receive a call when an emergency call is made and can then listen in on the call.</span></span>
6. <span data-ttu-id="be1a6-126">緊急通報が行われたときに通知するために、1人以上のユーザーまたはグループ (組織のセキュリティデスクなど) を検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="be1a6-126">Search for and select one or more users or groups, such as your organization's security desk, to notify when an emergency call is made.</span></span>  <span data-ttu-id="be1a6-127">通知は、ユーザー、配布グループ、セキュリティグループのメールアドレスに送信できます。</span><span class="sxs-lookup"><span data-stu-id="be1a6-127">The notification can be sent to email addresses of users, distribution groups, and security groups.</span></span> <span data-ttu-id="be1a6-128">通知できるユーザーの最大数は50です。</span><span class="sxs-lookup"><span data-stu-id="be1a6-128">A maximum of 50 users can be notified.</span></span>
7. <span data-ttu-id="be1a6-129">[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="be1a6-129">Click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="be1a6-130">PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="be1a6-130">Using PowerShell</span></span>

<span data-ttu-id="be1a6-131">「 [新規-CsTeamsEmergencyCallingPolicy」を](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy)参照してください。</span><span class="sxs-lookup"><span data-stu-id="be1a6-131">See [New-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy).</span></span>

## <a name="edit-an-emergency-calling-policy"></a><span data-ttu-id="be1a6-132">緊急通話のポリシーを編集する</span><span class="sxs-lookup"><span data-stu-id="be1a6-132">Edit an emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="be1a6-133">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="be1a6-133">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="be1a6-134">グローバル ポリシー、または作成したカスタム ポリシーを編集できます。</span><span class="sxs-lookup"><span data-stu-id="be1a6-134">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="be1a6-135">Microsoft Teams 管理センターの左のナビゲーションで、[**ボイス**  >  **緊急ポリシー**] に移動し、[**通話ポリシー** ] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="be1a6-135">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="be1a6-136">ポリシー名の左側をクリックしてポリシーを選び、**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="be1a6-136">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="be1a6-137">必要な変更を加えて、[ **適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="be1a6-137">Make the changes that you want, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="be1a6-138">PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="be1a6-138">Using PowerShell</span></span>

<span data-ttu-id="be1a6-139">「 [Set-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be1a6-139">See [Set-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy).</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a><span data-ttu-id="be1a6-140">ユーザーにカスタム緊急通話ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="be1a6-140">Assign a custom emergency calling policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="be1a6-141">「 [Grant-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy)」も参照してください。</span><span class="sxs-lookup"><span data-stu-id="be1a6-141">See also [Grant-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy).</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a><span data-ttu-id="be1a6-142">ユーザー設定の緊急通話ポリシーをネットワークサイトに割り当てる</span><span class="sxs-lookup"><span data-stu-id="be1a6-142">Assign a custom emergency calling policy to a network site</span></span>

<span data-ttu-id="be1a6-143">[CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite)コマンドレットを使用して、緊急通話ポリシーをネットワークサイトに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="be1a6-143">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) cmdlet to assign an emergency calling policy to a network site.</span></span>

<span data-ttu-id="be1a6-144">次の例は、Contoso 緊急通話ポリシー1と呼ばれるポリシーを Site1 サイトに割り当てる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="be1a6-144">The following example shows how to assign a policy called Contoso Emergency Calling Policy 1 to the Site1 site.</span></span>

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a><span data-ttu-id="be1a6-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="be1a6-145">Related topics</span></span>

[<span data-ttu-id="be1a6-146">Teams で緊急通話ルーティングポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="be1a6-146">Manage emergency call routing policies in Teams</span></span>](manage-emergency-call-routing-policies.md)

[<span data-ttu-id="be1a6-147">Teams での PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="be1a6-147">Teams PowerShell overview</span></span>](teams-powershell-overview.md)

[<span data-ttu-id="be1a6-148">チームのユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="be1a6-148">Assign policies to your users in Teams</span></span>](assign-policies.md)
