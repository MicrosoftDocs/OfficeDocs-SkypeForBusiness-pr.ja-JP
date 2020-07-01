---
title: 緊急通話のルーティング ポリシーを管理する
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords: ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 緊急電話番号を設定し、緊急電話のルーティング方法を指定するために、Microsoft Teams で緊急通話ルーティングポリシーを使用および管理する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 35595d8c3b784b908448eae72013cb8bcf3f37f7
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938166"
---
# <a name="manage-emergency-call-routing-policies-in-microsoft-teams"></a><span data-ttu-id="85755-103">Microsoft Teams で緊急通話ルーティングポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="85755-103">Manage emergency call routing policies in Microsoft Teams</span></span>

<span data-ttu-id="85755-104">組織で[電話システムのダイレクトルーティング](direct-routing-landing-page.md)を展開した場合は、Microsoft Teams の緊急通話ルーティングポリシーを使って緊急電話番号を設定し、緊急電話のルーティング方法を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="85755-104">If you've deployed [Phone System Direct Routing](direct-routing-landing-page.md) in your organization, you can use emergency call routing policies in Microsoft Teams to set up emergency numbers and specify how emergency calls are routed.</span></span> <span data-ttu-id="85755-105">緊急通話ルーティングポリシーは、ポリシーが割り当てられているユーザーに対して強化された緊急サービスが有効になっているかどうかを決定します。また、緊急サービスへの通話に使用する番号 (米国内の911など)、緊急サービスへの通話の発信方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="85755-105">An emergency call routing policy determines whether enhanced emergency services is enabled for users who are assigned the policy, the numbers used to call emergency services (for example, 911 in the United States), and how calls to emergency services are routed.</span></span>

<span data-ttu-id="85755-106">緊急通話のルーティングポリシーを管理するに**Voice**  >  は、Microsoft Teams 管理センターのボイス**緊急ポリシー**または Windows PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="85755-106">You manage emergency call routing policies by going to **Voice** > **Emergency policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span> <span data-ttu-id="85755-107">ポリシーは、ユーザーと[ネットワークサイト](cloud-voice-network-settings.md)に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="85755-107">The policies can be assigned to users and [network sites](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="85755-108">ユーザーの場合は、グローバル (組織全体の既定) ポリシーを使用するか、カスタムポリシーを作成して割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="85755-108">For users, you can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="85755-109">カスタムポリシーを作成して割り当てる場合を除き、ユーザーはグローバルポリシーを自動的に取得します。</span><span class="sxs-lookup"><span data-stu-id="85755-109">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="85755-110">グローバルポリシーの設定は編集できますが、名前の変更や削除はできないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="85755-110">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span> <span data-ttu-id="85755-111">ネットワークサイトの場合は、カスタムポリシーを作成して割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="85755-111">For network sites, you create and assign custom policies.</span></span>

<span data-ttu-id="85755-112">緊急通話ルーティングポリシーがネットワークサイトとユーザーに割り当てられている場合、そのユーザーがそのネットワークサイトを使用している場合、そのネットワークサイトに割り当てられているポリシーが、ユーザーに割り当てられているポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="85755-112">If you assigned an emergency call routing policy to a network site and to a user and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="create-a-custom-emergency-call-routing-policy"></a><span data-ttu-id="85755-113">ユーザー設定の緊急通話ルーティングポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="85755-113">Create a custom emergency call routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="85755-114">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="85755-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="85755-115">Microsoft Teams 管理センターの左のナビゲーションで、[**ボイス**  >  **緊急ポリシー**] に移動し、[**通話ルーティングポリシー** ] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="85755-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Call routing policies** tab.</span></span>
2. <span data-ttu-id="85755-116">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="85755-116">Click **Add**.</span></span>
3. <span data-ttu-id="85755-117">ポリシーの名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="85755-117">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="85755-118">動的緊急通話を有効にするには、**動的緊急通話**を有効にします。</span><span class="sxs-lookup"><span data-stu-id="85755-118">To enable dynamic emergency calling, turn on **Dynamic emergency calling**.</span></span> <span data-ttu-id="85755-119">動的な緊急通話が有効になっていると、チームはサービスからポリシーと場所情報を取得し、緊急通話の一部としてその情報を含めます。</span><span class="sxs-lookup"><span data-stu-id="85755-119">When dynamic emergency calling is enabled, Teams retrieves policy and location information from the service and includes that information as part of the emergency call.</span></span>
5. <span data-ttu-id="85755-120">1つまたは複数の緊急電話番号を定義します。</span><span class="sxs-lookup"><span data-stu-id="85755-120">Define one or more emergency numbers.</span></span> <span data-ttu-id="85755-121">これを行うには、[**緊急電話番号**] の [**追加**] をクリックし、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="85755-121">To do this, under **Emergency numbers**, click **Add**, and then do the following:</span></span>
    1. <span data-ttu-id="85755-122">**緊急ダイヤル文字列**: 緊急ダイヤルの文字列を入力します。</span><span class="sxs-lookup"><span data-stu-id="85755-122">**Emergency dial string**: Enter the emergency dial string.</span></span> <span data-ttu-id="85755-123">このダイヤル文字列は、通話が緊急通話であることを示します。</span><span class="sxs-lookup"><span data-stu-id="85755-123">This dial string indicates that a call is an emergency call.</span></span>
        > [!NOTE]
        > <span data-ttu-id="85755-124">ダイレクトルーティングの場合、緊急電話番号の前に「+」を付けて、Teams クライアントから緊急通報に移行しています。</span><span class="sxs-lookup"><span data-stu-id="85755-124">For Direct Routing, we're transitioning away from Teams clients sending emergency calls with a "+" in front of the emergency dial string.</span></span> <span data-ttu-id="85755-125">切り替えが完了するまでは、緊急ダイヤルの文字列に一致するボイスルートのパターンによって、911や + 911 などの前に "+" が含まれている文字列に一致していることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="85755-125">Until the transition is completed, the voice route pattern to match an emergency dial string should ensure a match is made for strings that have and don't have a preceding "+", such as 911 and +911.</span></span> <span data-ttu-id="85755-126">たとえば、^ \\ + 911 または. \* とします。</span><span class="sxs-lookup"><span data-stu-id="85755-126">For example, ^\\+?911 or .\*.</span></span>
    2. <span data-ttu-id="85755-127">**緊急ダイヤルマスク**: 緊急電話番号ごとに、0個以上の緊急ダイヤルマスクを指定できます。</span><span class="sxs-lookup"><span data-stu-id="85755-127">**Emergency dial mask**: For each emergency number, you can specify zero or more emergency dial masks.</span></span> <span data-ttu-id="85755-128">ダイヤルマスクは、緊急ダイヤルの文字列の値に変換する番号です。</span><span class="sxs-lookup"><span data-stu-id="85755-128">A dial mask is the number that you want to translate into the value of the emergency dial string.</span></span> <span data-ttu-id="85755-129">これにより、代替の緊急電話番号にダイヤルすることができます。また、緊急電話サービスにも通話を発信できます。</span><span class="sxs-lookup"><span data-stu-id="85755-129">This allows for alternate emergency numbers to be dialed and still have the call reach emergency services.</span></span> <br><span data-ttu-id="85755-130">たとえば、112を緊急ダイヤルのマスクとして追加します。これは、ヨーロッパのほとんどの緊急サービス番号であり、また、緊急ダイヤルの文字列として911です。</span><span class="sxs-lookup"><span data-stu-id="85755-130">For example, you add 112 as the emergency dial mask, which is the emergency service number for most of Europe, and 911 as the emergency dial string.</span></span> <span data-ttu-id="85755-131">他のヨーロッパの Teams ユーザーは、911が米国の緊急電話番号であることを知らない場合があります。また、112の場合は、911に発信されます。</span><span class="sxs-lookup"><span data-stu-id="85755-131">A Teams user from Europe who is visiting may not know that 911 is the emergency number in the United States, and when they dial 112, the call is made to 911.</span></span> <span data-ttu-id="85755-132">複数のダイヤルマスクを定義するには、各値をセミコロンで区切ります。</span><span class="sxs-lookup"><span data-stu-id="85755-132">To define multiple dial masks, separate each value by a semicolon.</span></span> <span data-ttu-id="85755-133">たとえば、112; 212 とします。</span><span class="sxs-lookup"><span data-stu-id="85755-133">For example, 112;212.</span></span>
    3. <span data-ttu-id="85755-134">[ **Pstn 使用状況] レコード**: 公衆交換電話網 (PSTN) 利用状況レコードを選択します。</span><span class="sxs-lookup"><span data-stu-id="85755-134">**PSTN usage record**: Select the Public Switched Telephone Network (PSTN) usage record.</span></span> <span data-ttu-id="85755-135">PSTN 使用を許可しているユーザーから緊急電話をルーティングするために使用するルートを決定するために、PSTN 使用状況レコードが使用されます。</span><span class="sxs-lookup"><span data-stu-id="85755-135">The PSTN usage record is used to determine which route is used to route emergency calls from users who are authorized to use them.</span></span> <span data-ttu-id="85755-136">この用途に関連付けられているルートは、緊急通報専用のセッション開始プロトコル (SIP) トランク、または最も近い公共の安全な応答ポイント (PSAP) に緊急通話をルーティングする緊急対応の場所識別番号 (ELIN) ゲートウェイを指している必要があります。</span><span class="sxs-lookup"><span data-stu-id="85755-136">The route associated with this usage should point to a Session Initiation Protocol (SIP) trunk dedicated to emergency calls or to an Emergency Location Identification Number (ELIN) gateway that routes emergency calls to the nearest Public Safety Answering Point (PSAP).</span></span>

    > [!NOTE]
    > <span data-ttu-id="85755-137">ダイヤル文字列とダイヤルマスクは、ポリシー内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="85755-137">Dial strings and dial masks must be unique within a policy.</span></span> <span data-ttu-id="85755-138">つまり、ポリシーの場合、複数の緊急電話番号を定義できますが、ダイヤルする文字列に複数のダイヤルマスクを設定することはできますが、各ダイヤル文字列とダイヤルマスクは1回のみ使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="85755-138">This means that for a policy, you can define multiple emergency numbers and you can set multiple dial masks for a dial string, but each dial string and dial mask must only be used one time.</span></span>

6. <span data-ttu-id="85755-139">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="85755-139">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="85755-140">PowerShell を使用する場合</span><span class="sxs-lookup"><span data-stu-id="85755-140">Using PowerShell</span></span>

<span data-ttu-id="85755-141">「[新規-CsTeamsEmergencyCallRoutingPolicy」を](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallroutingpolicy)参照してください。</span><span class="sxs-lookup"><span data-stu-id="85755-141">See [New-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallroutingpolicy).</span></span>

## <a name="edit-an-emergency-call-routing-policy"></a><span data-ttu-id="85755-142">緊急通話ルーティングポリシーを編集する</span><span class="sxs-lookup"><span data-stu-id="85755-142">Edit an emergency call routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="85755-143">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="85755-143">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="85755-144">グローバル ポリシー、または作成したカスタム ポリシーを編集できます。</span><span class="sxs-lookup"><span data-stu-id="85755-144">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="85755-145">Microsoft Teams 管理センターの左のナビゲーションで、[**ボイス**  >  **緊急ポリシー**] に移動し、[**通話ルーティングポリシー** ] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="85755-145">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Call routing policies** tab.</span></span>
2. <span data-ttu-id="85755-146">ポリシー名の左側をクリックしてポリシーを選び、**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="85755-146">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="85755-147">必要な変更を加えて、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="85755-147">Make the changes that you want, and then click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="85755-148">PowerShell を使用する場合</span><span class="sxs-lookup"><span data-stu-id="85755-148">Using PowerShell</span></span>

<span data-ttu-id="85755-149">「 [Set-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallroutingpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85755-149">See [Set-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallroutingpolicy).</span></span>

## <a name="assign-a-custom-emergency-call-routing-policy-to-users"></a><span data-ttu-id="85755-150">ユーザーにカスタム緊急通話ルーティングポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="85755-150">Assign a custom emergency call routing policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="85755-151">「 [Grant-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallroutingpolicy)」も参照してください。</span><span class="sxs-lookup"><span data-stu-id="85755-151">See also [Grant-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallroutingpolicy).</span></span>

## <a name="assign-a-custom-emergency-call-routing-policy-to-a-network-site"></a><span data-ttu-id="85755-152">ユーザー設定の緊急通話ルーティングポリシーをネットワークサイトに割り当てる</span><span class="sxs-lookup"><span data-stu-id="85755-152">Assign a custom emergency call routing policy to a network site</span></span>

<span data-ttu-id="85755-153">[CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite)コマンドレットを使用して、緊急通話ルーティングポリシーをネットワークサイトに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="85755-153">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) cmdlet to assign an emergency calling routing policy to a network site.</span></span>

<span data-ttu-id="85755-154">次の例は、緊急通話ルーティングポリシー1と呼ばれるポリシーを Site1 サイトに割り当てる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="85755-154">This example shows how to assign a policy called Emergency Call Routing Policy 1 to the Site1 site.</span></span>

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Emergency Call Routing Policy 1"
```

## <a name="related-topics"></a><span data-ttu-id="85755-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="85755-155">Related topics</span></span>

[<span data-ttu-id="85755-156">Teams で緊急通話のポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="85755-156">Manage emergency calling policies in Teams</span></span>](manage-emergency-calling-policies.md)

[<span data-ttu-id="85755-157">Teams での PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="85755-157">Teams PowerShell overview</span></span>](teams-powershell-overview.md)

[<span data-ttu-id="85755-158">チームのユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="85755-158">Assign policies to your users in Teams</span></span>](assign-policies.md)
