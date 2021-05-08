---
title: 緊急通話のルーティング ポリシーを管理する
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams で緊急通話ルーティング ポリシーを使用および管理して緊急電話番号を設定し、緊急通話のルーティング方法を指定する方法について説明します。
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.openlocfilehash: 0fb3a80bf5c1a064435754c4f999f6a62214b021
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096181"
---
# <a name="manage-emergency-call-routing-policies-in-microsoft-teams"></a><span data-ttu-id="39981-103">緊急通話ルーティング ポリシーを管理Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="39981-103">Manage emergency call routing policies in Microsoft Teams</span></span>

<span data-ttu-id="39981-104">組織内に[電話システム ダイレクト](direct-routing-landing-page.md)ルーティングをデプロイしている場合は、Microsoft Teams の緊急通話ルーティング ポリシーを使用して緊急電話番号を設定し、緊急通話のルーティング方法を指定できます。</span><span class="sxs-lookup"><span data-stu-id="39981-104">If you've deployed [Phone System Direct Routing](direct-routing-landing-page.md) in your organization, you can use emergency call routing policies in Microsoft Teams to set up emergency numbers and specify how emergency calls are routed.</span></span> <span data-ttu-id="39981-105">緊急通話ルーティング ポリシーは、ポリシーが割り当てられているユーザーに対して強化された緊急サービスを有効にするかどうか、緊急サービスの呼び出しに使用される番号 (米国では 911 など)、緊急サービスへの呼び出しのルーティング方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="39981-105">An emergency call routing policy determines whether enhanced emergency services is enabled for users who are assigned the policy, the numbers used to call emergency services (for example, 911 in the United States), and how calls to emergency services are routed.</span></span>

<span data-ttu-id="39981-106">緊急通話ルーティング ポリシーを管理するには、Microsoft Teams管理センターで音声緊急ポリシーに移動するか  >  、Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="39981-106">You manage emergency call routing policies by going to **Voice** > **Emergency policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span> <span data-ttu-id="39981-107">ポリシーは、ユーザーとネットワーク サイトに [割り当てることができます](cloud-voice-network-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="39981-107">The policies can be assigned to users and [network sites](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="39981-108">ユーザーの場合は、グローバル (組織全体の既定) ポリシーを使用するか、カスタム ポリシーを作成して割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="39981-108">For users, you can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="39981-109">カスタム ポリシーを作成して割り当てない限り、ユーザーは自動的にグローバル ポリシーを取得します。</span><span class="sxs-lookup"><span data-stu-id="39981-109">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="39981-110">グローバル ポリシーの設定は編集できますが、名前の変更や削除はできないので、ご安心ください。</span><span class="sxs-lookup"><span data-stu-id="39981-110">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span> <span data-ttu-id="39981-111">ネットワーク サイトの場合は、カスタム ポリシーを作成して割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="39981-111">For network sites, you create and assign custom policies.</span></span>

<span data-ttu-id="39981-112">緊急通話ルーティング ポリシーをネットワーク サイトとユーザーに割り当て、そのユーザーがネットワーク サイトに割り当てられている場合、ネットワーク サイトに割り当てられているポリシーは、ユーザーに割り当てられているポリシーを上書きします。</span><span class="sxs-lookup"><span data-stu-id="39981-112">If you assigned an emergency call routing policy to a network site and to a user and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="create-a-custom-emergency-call-routing-policy"></a><span data-ttu-id="39981-113">カスタム緊急通話ルーティング ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="39981-113">Create a custom emergency call routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="39981-114">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="39981-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="39981-115">管理センターの左側のナビゲーションMicrosoft Teams[**音声緊急対応** ポリシー] に移動し、[通話ルーティング ポリシー] タブ  >  **をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="39981-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Call routing policies** tab.</span></span>
2. <span data-ttu-id="39981-116">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39981-116">Click **Add**.</span></span>
3. <span data-ttu-id="39981-117">ポリシーの名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="39981-117">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="39981-118">動的緊急通話を有効にするには、動的緊急通話 **を有効にしてください**。</span><span class="sxs-lookup"><span data-stu-id="39981-118">To enable dynamic emergency calling, turn on **Dynamic emergency calling**.</span></span> <span data-ttu-id="39981-119">動的緊急通話が有効になっている場合、Teams サービスからポリシーと場所の情報を取得し、その情報を緊急通話の一部として含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="39981-119">When dynamic emergency calling is enabled, Teams retrieves policy and location information from the service and includes that information as part of the emergency call.</span></span>
5. <span data-ttu-id="39981-120">1 つ以上の緊急電話番号を定義します。</span><span class="sxs-lookup"><span data-stu-id="39981-120">Define one or more emergency numbers.</span></span> <span data-ttu-id="39981-121">これを行うには、[緊急電話番号] **で**[追加] を **クリックし**、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="39981-121">To do this, under **Emergency numbers**, click **Add**, and then do the following:</span></span>
    1. <span data-ttu-id="39981-122">**[緊急ダイヤル文字列**]: 緊急ダイヤル文字列を入力します。</span><span class="sxs-lookup"><span data-stu-id="39981-122">**Emergency dial string**: Enter the emergency dial string.</span></span> <span data-ttu-id="39981-123">このダイヤル文字列は、通話が緊急通話を示します。</span><span class="sxs-lookup"><span data-stu-id="39981-123">This dial string indicates that a call is an emergency call.</span></span>
        > [!NOTE]
        > <span data-ttu-id="39981-124">ダイレクト ルーティングでは、緊急ダイヤル文字列の前に "+" Teams を使用して緊急通話を送信するクライアントから移行します。</span><span class="sxs-lookup"><span data-stu-id="39981-124">For Direct Routing, we're transitioning away from Teams clients sending emergency calls with a "+" in front of the emergency dial string.</span></span> <span data-ttu-id="39981-125">切り替えが完了するまで、緊急ダイヤル文字列に一致する音声ルート パターンは、911 や +911 など、前の "+" を持つ文字列とない文字列に対して一致が行われます。</span><span class="sxs-lookup"><span data-stu-id="39981-125">Until the transition is completed, the voice route pattern to match an emergency dial string should ensure a match is made for strings that have and don't have a preceding "+", such as 911 and +911.</span></span> <span data-ttu-id="39981-126">例: ^ \\ +?911 または .\*。</span><span class="sxs-lookup"><span data-stu-id="39981-126">For example, ^\\+?911 or .\*.</span></span>
    2. <span data-ttu-id="39981-127">**緊急ダイヤル マスク**: 緊急電話番号ごとに、0 個以上の緊急ダイヤル マスクを指定できます。</span><span class="sxs-lookup"><span data-stu-id="39981-127">**Emergency dial mask**: For each emergency number, you can specify zero or more emergency dial masks.</span></span> <span data-ttu-id="39981-128">ダイヤル マスクは、緊急ダイヤル文字列の値に変換する番号です。</span><span class="sxs-lookup"><span data-stu-id="39981-128">A dial mask is the number that you want to translate into the value of the emergency dial string.</span></span> <span data-ttu-id="39981-129">これにより、代替の緊急電話番号をダイヤルし、通話が緊急サービスに届く可能性があります。</span><span class="sxs-lookup"><span data-stu-id="39981-129">This allows for alternate emergency numbers to be dialed and still have the call reach emergency services.</span></span> <br><span data-ttu-id="39981-130">たとえば、緊急ダイヤル マスクとして 112 を追加します。これはヨーロッパの大部分の緊急サービス番号で、911 を緊急ダイヤル文字列として追加します。</span><span class="sxs-lookup"><span data-stu-id="39981-130">For example, you add 112 as the emergency dial mask, which is the emergency service number for most of Europe, and 911 as the emergency dial string.</span></span> <span data-ttu-id="39981-131">ヨーロッパTeamsしているユーザーは、911 が米国の緊急電話番号であり、112 をダイヤルすると 911 に発信されます。</span><span class="sxs-lookup"><span data-stu-id="39981-131">A Teams user from Europe who is visiting may not know that 911 is the emergency number in the United States, and when they dial 112, the call is made to 911.</span></span> <span data-ttu-id="39981-132">複数のダイヤル マスクを定義するには、各値をセミコロンで区切ります。</span><span class="sxs-lookup"><span data-stu-id="39981-132">To define multiple dial masks, separate each value by a semicolon.</span></span> <span data-ttu-id="39981-133">たとえば、112;212 です。</span><span class="sxs-lookup"><span data-stu-id="39981-133">For example, 112;212.</span></span>
    3. <span data-ttu-id="39981-134">**PSTN 使用レコード**: 公衆交換電話網 (PSTN) 使用レコードを選択します。</span><span class="sxs-lookup"><span data-stu-id="39981-134">**PSTN usage record**: Select the Public Switched Telephone Network (PSTN) usage record.</span></span> <span data-ttu-id="39981-135">PSTN 使用状況レコードは、使用が承認されているユーザーからの緊急通話をルーティングするために使用されるルートを決定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="39981-135">The PSTN usage record is used to determine which route is used to route emergency calls from users who are authorized to use them.</span></span> <span data-ttu-id="39981-136">この使用に関連付けられているルートは、緊急通話専用のセッション開始プロトコル (SIP) トランク、または緊急通話を最も近い公衆安全応答ポイント (PSAP) にルーティングする緊急場所識別番号 (ELIN) ゲートウェイを指す必要があります。</span><span class="sxs-lookup"><span data-stu-id="39981-136">The route associated with this usage should point to a Session Initiation Protocol (SIP) trunk dedicated to emergency calls or to an Emergency Location Identification Number (ELIN) gateway that routes emergency calls to the nearest Public Safety Answering Point (PSAP).</span></span>

    > [!NOTE]
    > <span data-ttu-id="39981-137">ダイヤル文字列とダイヤル マスクは、ポリシー内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="39981-137">Dial strings and dial masks must be unique within a policy.</span></span> <span data-ttu-id="39981-138">つまり、ポリシーでは複数の緊急電話番号を定義し、ダイヤル文字列に複数のダイヤル マスクを設定できますが、各ダイヤル文字列とダイヤル マスクは 1 回のみ使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="39981-138">This means that for a policy, you can define multiple emergency numbers and you can set multiple dial masks for a dial string, but each dial string and dial mask must only be used one time.</span></span>

6. <span data-ttu-id="39981-139">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39981-139">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="39981-140">PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="39981-140">Using PowerShell</span></span>

<span data-ttu-id="39981-141">[New-CsTeamsEmergencyCallRoutingPolicy を参照してください](/powershell/module/skype/new-csteamsemergencycallroutingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="39981-141">See [New-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/new-csteamsemergencycallroutingpolicy).</span></span>

## <a name="edit-an-emergency-call-routing-policy"></a><span data-ttu-id="39981-142">緊急通話ルーティング ポリシーを編集する</span><span class="sxs-lookup"><span data-stu-id="39981-142">Edit an emergency call routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="39981-143">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="39981-143">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="39981-144">グローバル ポリシー、または作成したカスタム ポリシーを編集できます。</span><span class="sxs-lookup"><span data-stu-id="39981-144">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="39981-145">管理センターの左側のナビゲーションMicrosoft Teams[**音声緊急対応** ポリシー] に移動し、[通話ルーティング ポリシー] タブ  >  **をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="39981-145">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Call routing policies** tab.</span></span>
2. <span data-ttu-id="39981-146">ポリシー名の左側をクリックしてポリシーを選び、**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39981-146">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="39981-147">必要な変更を行い、[保存] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="39981-147">Make the changes that you want, and then click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="39981-148">PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="39981-148">Using PowerShell</span></span>

<span data-ttu-id="39981-149">[「Set-CsTeamsEmergencyCallRoutingPolicy」を参照してください](/powershell/module/skype/set-csteamsemergencycallroutingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="39981-149">See [Set-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/set-csteamsemergencycallroutingpolicy).</span></span>

## <a name="assign-a-custom-emergency-call-routing-policy-to-users"></a><span data-ttu-id="39981-150">カスタム緊急通話ルーティング ポリシーをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="39981-150">Assign a custom emergency call routing policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="39981-151">[Grant-CsTeamsEmergencyCallRoutingPolicy も参照してください](/powershell/module/skype/grant-csteamsemergencycallroutingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="39981-151">See also [Grant-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/grant-csteamsemergencycallroutingpolicy).</span></span>

## <a name="assign-a-custom-emergency-call-routing-policy-to-a-network-site"></a><span data-ttu-id="39981-152">カスタム緊急通話ルーティング ポリシーをネットワーク サイトに割り当てる</span><span class="sxs-lookup"><span data-stu-id="39981-152">Assign a custom emergency call routing policy to a network site</span></span>

<span data-ttu-id="39981-153">[Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite)コマンドレットを使用して、緊急通話ルーティング ポリシーをネットワーク サイトに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="39981-153">Use the [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) cmdlet to assign an emergency calling routing policy to a network site.</span></span>

<span data-ttu-id="39981-154">この例では、緊急通話ルーティング ポリシー 1 というポリシーを Site1 サイトに割り当てる方法を示します。</span><span class="sxs-lookup"><span data-stu-id="39981-154">This example shows how to assign a policy called Emergency Call Routing Policy 1 to the Site1 site.</span></span>

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Emergency Call Routing Policy 1"
```

## <a name="related-topics"></a><span data-ttu-id="39981-155">関連トピック</span><span class="sxs-lookup"><span data-stu-id="39981-155">Related topics</span></span>

[<span data-ttu-id="39981-156">緊急通話ポリシーを管理Teams</span><span class="sxs-lookup"><span data-stu-id="39981-156">Manage emergency calling policies in Teams</span></span>](manage-emergency-calling-policies.md)

[<span data-ttu-id="39981-157">Teams での PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="39981-157">Teams PowerShell overview</span></span>](teams-powershell-overview.md)

[<span data-ttu-id="39981-158"> Teams でユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="39981-158">Assign policies to your users in Teams</span></span>](assign-policies.md)