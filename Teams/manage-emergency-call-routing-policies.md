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
ms.openlocfilehash: cf47bc27ddc72d6f767815b5323b69f6e5fd00ca
ms.sourcegitcommit: ee2b4c207b3c9f993309f66cf8016e137c001c7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2020
ms.locfileid: "44350211"
---
# <a name="manage-emergency-call-routing-policies-in-microsoft-teams"></a><span data-ttu-id="2f898-103">Microsoft Teams で緊急通話ルーティングポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="2f898-103">Manage emergency call routing policies in Microsoft Teams</span></span>

<span data-ttu-id="2f898-104">組織で電話システムのダイレクトルーティングを展開した場合は、Microsoft Teams の緊急通話ルーティングポリシーを使って緊急電話番号を設定し、緊急電話のルーティング方法を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="2f898-104">If you've deployed Phone System Direct Routing in your organization, you can use emergency call routing policies in Microsoft Teams to set up emergency numbers and specify how emergency calls are routed.</span></span> <span data-ttu-id="2f898-105">緊急通話ルーティングポリシーは、ポリシーが割り当てられているユーザーに対して強化された緊急サービスが有効になっているかどうかを決定します。また、緊急サービスへの通話に使用する番号 (米国内の911など)、緊急サービスへの通話の発信方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="2f898-105">An emergency call routing policy determines whether enhanced emergency services is enabled for users who are assigned the policy, the numbers used to call emergency services (for example, 911 in the United States), and how calls to emergency services are routed.</span></span>

<span data-ttu-id="2f898-106">緊急通話のルーティングポリシーを管理するに**Voice**  >  は、Microsoft Teams 管理センターのボイス**緊急ポリシー**または Windows PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="2f898-106">You manage emergency call routing policies by going to **Voice** > **Emergency policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span> <span data-ttu-id="2f898-107">ポリシーは、ユーザーと[ネットワークサイト](cloud-voice-network-settings.md)に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="2f898-107">The policies can be assigned to users and [network sites](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="2f898-108">ユーザーの場合は、グローバル (組織全体の既定) ポリシーを使用するか、カスタムポリシーを作成して割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="2f898-108">For users, you can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="2f898-109">カスタムポリシーを作成して割り当てる場合を除き、ユーザーはグローバルポリシーを自動的に取得します。</span><span class="sxs-lookup"><span data-stu-id="2f898-109">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="2f898-110">グローバルポリシーの設定は編集できますが、名前の変更や削除はできないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="2f898-110">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span> <span data-ttu-id="2f898-111">ネットワークサイトの場合は、カスタムポリシーを作成して割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f898-111">For network sites, you create and assign custom policies.</span></span>

<span data-ttu-id="2f898-112">緊急通話ルーティングポリシーがネットワークサイトとユーザーに割り当てられている場合、そのユーザーがそのネットワークサイトを使用している場合、そのネットワークサイトに割り当てられているポリシーが、ユーザーに割り当てられているポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="2f898-112">If you assigned an emergency call routing policy to a network site and to a user and if that  user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="create-a-custom-emergency-call-routing-policy"></a><span data-ttu-id="2f898-113">ユーザー設定の緊急通話ルーティングポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="2f898-113">Create a custom emergency call routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="2f898-114">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="2f898-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="2f898-115">Microsoft Teams 管理センターの左のナビゲーションで、[**ボイス**  >  **緊急ポリシー**] に移動し、[**通話ルーティングポリシー** ] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="2f898-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Call routing policies** tab.</span></span>
2. <span data-ttu-id="2f898-116">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2f898-116">Click **Add**.</span></span>
3. <span data-ttu-id="2f898-117">ポリシーの名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="2f898-117">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="2f898-118">Enhanced エマージェンシー・サービスを有効にするには、強化された**エマージェンシー・サービス**を有効にします。</span><span class="sxs-lookup"><span data-stu-id="2f898-118">To enable enhanced emergency services, turn on **Enhanced emergency services**.</span></span> <span data-ttu-id="2f898-119">強化された緊急サービスが有効になっていると、チームはサービスからポリシーと場所情報を取得し、緊急通話の一部としてその情報を含めます。</span><span class="sxs-lookup"><span data-stu-id="2f898-119">When enhanced emergency services is enabled, Teams retrieves policy and location information from the service and includes that information as part of the emergency call.</span></span>
5. <span data-ttu-id="2f898-120">緊急電話番号のいずれかを定義します。</span><span class="sxs-lookup"><span data-stu-id="2f898-120">Define one of more emergency numbers.</span></span> <span data-ttu-id="2f898-121">これを行うには、[**緊急電話番号**] の下で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="2f898-121">To do this, under **Emergency numbers**, do the following:</span></span>
    1. <span data-ttu-id="2f898-122">**緊急ダイヤル文字列**: 緊急ダイヤルの文字列を入力します。</span><span class="sxs-lookup"><span data-stu-id="2f898-122">**Emergency dial string**: Enter the emergency dial string.</span></span> <span data-ttu-id="2f898-123">このダイヤル文字列は、通話が緊急通話であることを示します。</span><span class="sxs-lookup"><span data-stu-id="2f898-123">This dial string indicates that a call is an emergency call.</span></span>
        > [!NOTE]
        > <span data-ttu-id="2f898-124">ダイレクトルーティングの場合、緊急電話番号の前に「+」を付けて、Teams クライアントから緊急通報に移行しています。</span><span class="sxs-lookup"><span data-stu-id="2f898-124">For Direct Routing, we're transitioning away from Teams clients sending emergency calls with a "+" in front of the emergency dial string.</span></span> <span data-ttu-id="2f898-125">切り替えが完了するまでは、緊急ダイヤルの文字列に一致するボイスルートのパターンによって、911や + 911 などの前に "+" が含まれている文字列に一致していることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f898-125">Until the transition is completed, the voice route pattern to match an emergency dial string should ensure a match is made for strings that have and don't have a preceding "+", such as 911 and +911.</span></span> <span data-ttu-id="2f898-126">たとえば、^ \\ + 911 または. \* とします。</span><span class="sxs-lookup"><span data-stu-id="2f898-126">For example, ^\\+?911 or .\*.</span></span>
    2. <span data-ttu-id="2f898-127">**緊急ダイヤルマスク**: 緊急電話番号ごとに、0個以上の緊急ダイヤルマスクを指定できます。</span><span class="sxs-lookup"><span data-stu-id="2f898-127">**Emergency dial mask**: For each emergency number, you can specify zero or more emergency dial masks.</span></span> <span data-ttu-id="2f898-128">ダイヤルマスクは、緊急ダイヤルの文字列の値に変換する番号です。</span><span class="sxs-lookup"><span data-stu-id="2f898-128">A dial mask is the number that you want to translate into the value of the emergency dial string.</span></span> <span data-ttu-id="2f898-129">これにより、代替の緊急電話番号にダイヤルすることができます。また、緊急電話サービスにも通話を発信できます。</span><span class="sxs-lookup"><span data-stu-id="2f898-129">This allows for alternate emergency numbers to be dialed and still have the call reach emergency services.</span></span> <br><span data-ttu-id="2f898-130">たとえば、112を緊急ダイヤルのマスクとして追加します。これは、ヨーロッパのほとんどの緊急サービス番号であり、また、緊急ダイヤルの文字列として911です。</span><span class="sxs-lookup"><span data-stu-id="2f898-130">For example, you add 112 as the emergency dial mask, which is the emergency service number for most of Europe, and 911 as the emergency dial string.</span></span> <span data-ttu-id="2f898-131">他のヨーロッパの Teams ユーザーは、911が米国の緊急電話番号であることを知らない場合があります。また、112の場合は、911に発信されます。</span><span class="sxs-lookup"><span data-stu-id="2f898-131">A Teams user from Europe who is visiting may not know that 911 is the emergency number in the United States, and when they dial 112, the call is made to 911.</span></span> <span data-ttu-id="2f898-132">複数のダイヤルマスクを定義するには、各値をセミコロンで区切ります。</span><span class="sxs-lookup"><span data-stu-id="2f898-132">To define multiple dial masks, separate each value by a semicolon.</span></span> <span data-ttu-id="2f898-133">たとえば、112; 212 とします。</span><span class="sxs-lookup"><span data-stu-id="2f898-133">For example, 112;212.</span></span>
    3. <span data-ttu-id="2f898-134">[ **Pstn 使用状況**]: 公衆交換電話網 (PSTN) 使用量を選択します。</span><span class="sxs-lookup"><span data-stu-id="2f898-134">**PSTN Usage**: Select the public switched telephone network (PSTN) usage.</span></span> <span data-ttu-id="2f898-135">PSTN の使用が許可されているユーザーから緊急通話をルーティングするために使用されるルートを決定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="2f898-135">The PSTN usage is used to determine which route is used to route emergency calls from users who are authorized to use them.</span></span> <span data-ttu-id="2f898-136">この使用に関連するルートは、緊急通報専用の SIP トランク、または最も近い公共の安全な応答ポイント (PSAP) に緊急通話をルーティングする緊急電話番号 (ELIN) のゲートウェイを指すようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f898-136">The route associated with this usage should point to an SIP trunk dedicated to emergency calls or to an Emergency Location Identification Number (ELIN) gateway that routes emergency calls to the nearest Public Safety Answering Point (PSAP).</span></span>

    > [!NOTE]
    > <span data-ttu-id="2f898-137">ダイヤル文字列とダイヤルマスクは、ポリシー内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f898-137">Dial strings and dial masks must be unique within a policy.</span></span> <span data-ttu-id="2f898-138">つまり、ポリシーの場合、複数の緊急電話番号を定義できますが、ダイヤルする文字列に複数のダイヤルマスクを設定することはできますが、各ダイヤル文字列とダイヤルマスクは1回のみ使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f898-138">This means that for a policy, you can define multiple emergency numbers and you can set multiple dial masks for a dial string, but each dial string and dial mask must only be used one time.</span></span>

6. <span data-ttu-id="2f898-139">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2f898-139">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="2f898-140">PowerShell を使用する場合</span><span class="sxs-lookup"><span data-stu-id="2f898-140">Using PowerShell</span></span>

<span data-ttu-id="2f898-141">「[新規-CsTeamsEmergencyCallRoutingPolicy」を](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallroutingpolicy)参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f898-141">See [New-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallroutingpolicy).</span></span>

## <a name="edit-an-emergency-call-routing-policy"></a><span data-ttu-id="2f898-142">緊急通話ルーティングポリシーを編集する</span><span class="sxs-lookup"><span data-stu-id="2f898-142">Edit an emergency call routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="2f898-143">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="2f898-143">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="2f898-144">グローバル ポリシー、または作成したカスタム ポリシーを編集できます。</span><span class="sxs-lookup"><span data-stu-id="2f898-144">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="2f898-145">Microsoft Teams 管理センターの左のナビゲーションで、[**ボイス**  >  **緊急ポリシー**] に移動し、[**通話ルーティングポリシー** ] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="2f898-145">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Call routing policies** tab.</span></span>
2. <span data-ttu-id="2f898-146">ポリシー名の左側をクリックしてポリシーを選び、**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2f898-146">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="2f898-147">必要な変更を加えて、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2f898-147">Make the changes that you want, and then click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="2f898-148">PowerShell を使用する場合</span><span class="sxs-lookup"><span data-stu-id="2f898-148">Using PowerShell</span></span>

<span data-ttu-id="2f898-149">「 [Set-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallroutingpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f898-149">See [Set-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallroutingpolicy).</span></span>

## <a name="assign-a-custom-emergency-call-routing-policy-to-users"></a><span data-ttu-id="2f898-150">ユーザーにカスタム緊急通話ルーティングポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="2f898-150">Assign a custom emergency call routing policy to users</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="2f898-151">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="2f898-151">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="2f898-152">1人のユーザーにポリシーを割り当てるには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="2f898-152">To assign a policy to one user:</span></span>

1. <span data-ttu-id="2f898-153">Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動してユーザーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="2f898-153">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="2f898-154">**[ポリシー]** をクリックし、**[割り当てられたポリシー]** の横にある **[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2f898-154">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="2f898-155">[**緊急着信ルーティングポリシー**] で、割り当てるポリシーを選び、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2f898-155">Under **Emergency call routing policy**, select the policy you want to assign, and then click **Save**.</span></span>

<span data-ttu-id="2f898-156">複数のユーザーに同時にポリシーを割り当てるには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="2f898-156">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="2f898-157">Microsoft Teams 管理センターの左のナビゲーションで [**ユーザー**] に移動し、ユーザーを検索するか、ビューをフィルター処理して、目的のユーザーを表示します。</span><span class="sxs-lookup"><span data-stu-id="2f898-157">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="2f898-158">[ **&#x2713;** (チェックマーク)] 列で、ユーザーを選びます。</span><span class="sxs-lookup"><span data-stu-id="2f898-158">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="2f898-159">すべてのユーザーを選択するには、テーブルの上部にある &#x2713; (チェックマーク) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2f898-159">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="2f898-160">[**設定の編集**] をクリックし、必要な変更を加えて、[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2f898-160">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>  

<span data-ttu-id="2f898-161">または、次の操作も実行できます。</span><span class="sxs-lookup"><span data-stu-id="2f898-161">Or, you can also do the following:</span></span>

1. <span data-ttu-id="2f898-162">Microsoft Teams 管理センターの左のナビゲーションで、[**ボイス**  >  **緊急ポリシー**] に移動し、[**通話ルーティングポリシー** ] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="2f898-162">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Call routing policies** tab.</span></span>
2. <span data-ttu-id="2f898-163">ポリシー名の左側をクリックしてポリシーを選びます。</span><span class="sxs-lookup"><span data-stu-id="2f898-163">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="2f898-164">[**ユーザーを管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2f898-164">Select **Manage users**.</span></span>
4. <span data-ttu-id="2f898-165">[**ユーザーを管理**] ウィンドウで、表示名またはユーザー名でユーザーを検索し、名前を選択して [**追加**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="2f898-165">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="2f898-166">追加するユーザーごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="2f898-166">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="2f898-167">ユーザーの追加が完了したら、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2f898-167">When you're finished adding users, click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="2f898-168">PowerShell を使用する場合</span><span class="sxs-lookup"><span data-stu-id="2f898-168">Using PowerShell</span></span>

#### <a name="assign-a-custom-emergency-call-routing-policy-to-a-user"></a><span data-ttu-id="2f898-169">ユーザーにカスタム緊急通話ルーティングポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="2f898-169">Assign a custom emergency call routing policy to a user</span></span>

<span data-ttu-id="2f898-170">「 [Grant-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallroutingpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f898-170">See [Grant-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallroutingpolicy).</span></span>

### <a name="assign-a-custom-emergency-call-routing-policy-to-users-in-a-group"></a><span data-ttu-id="2f898-171">ユーザー設定の緊急通話ルーティングポリシーをグループ内のユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="2f898-171">Assign a custom emergency call routing policy to users in a group</span></span>

<span data-ttu-id="2f898-172">ユーザーが既に識別している複数のユーザーに緊急通話ルーティングポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="2f898-172">You may want to assign a custom emergency call routing policy to multiple users that you've already identified.</span></span> <span data-ttu-id="2f898-173">たとえば、セキュリティグループまたは配布グループ内のすべてのユーザーにポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="2f898-173">For example, you may want to assign a policy to all users in a security or distribution group.</span></span> <span data-ttu-id="2f898-174">これを行うには、Graph 用 Azure Active Directory PowerShell モジュールと Skype for Business PowerShell モジュールに接続します。</span><span class="sxs-lookup"><span data-stu-id="2f898-174">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span>

<span data-ttu-id="2f898-175">この例では、Contoso の HR グループのすべてのユーザーに、HR 緊急通話ルーティングポリシーと呼ばれるポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="2f898-175">In this example, we assign a policy called HR Emergency Call Routing Policy to all users in the Contoso HR group.</span></span>  

> [!NOTE]
> <span data-ttu-id="2f898-176">「[単一の Windows PowerShell ウィンドウですべての Office 365 サービスに接続する](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)」の手順に従って、必ず最初に Azure Active Directory PowerShell for Graph モジュールと Skype for Business PowerShell モジュールに接続してください。</span><span class="sxs-lookup"><span data-stu-id="2f898-176">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="2f898-177">特定のグループの GroupObjectId を取得します。</span><span class="sxs-lookup"><span data-stu-id="2f898-177">Get the GroupObjectId of the particular group.</span></span>
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso HR"
```
<span data-ttu-id="2f898-178">指定したグループのメンバーを取得します。</span><span class="sxs-lookup"><span data-stu-id="2f898-178">Get the members of the specified group.</span></span>
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="2f898-179">グループ内のすべてのユーザーを特定のチーム ポリシーに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="2f898-179">Assign all users in the group to a particular teams policy.</span></span> <span data-ttu-id="2f898-180">この例では、HR 緊急通話ルーティングポリシーが使用されています。</span><span class="sxs-lookup"><span data-stu-id="2f898-180">In this example, it's HR Emergency Call Routing Policy.</span></span>
```PowerShell
$members | ForEach-Object {Grant-CsTeamsEmergencyCallRoutingPolicy -PolicyName "HR Emergency Call Routing Policy" -Identity $_.UserPrincipalName}
``` 
<span data-ttu-id="2f898-181">グループ内のメンバー数によっては、このコマンドの実行に数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="2f898-181">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="assign-a-custom-emergency-call-routing-policy-to-a-network-site"></a><span data-ttu-id="2f898-182">ユーザー設定の緊急通話ルーティングポリシーをネットワークサイトに割り当てる</span><span class="sxs-lookup"><span data-stu-id="2f898-182">Assign a custom emergency call routing policy to a network site</span></span>

<span data-ttu-id="2f898-183">[CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite)コマンドレットを使用して、緊急通話ルーティングポリシーをネットワークサイトに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="2f898-183">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) cmdlet to assign an emergency calling routing policy to a network site.</span></span>

<span data-ttu-id="2f898-184">次の例は、緊急通話ルーティングポリシー1と呼ばれるポリシーを Site1 サイトに割り当てる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="2f898-184">This example shows how to assign a policy called Emergency Call Routing Policy 1 to the Site1 site.</span></span>

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Emergency Call Routing Policy 1"
```

## <a name="related-topics"></a><span data-ttu-id="2f898-185">関連トピック</span><span class="sxs-lookup"><span data-stu-id="2f898-185">Related topics</span></span>

- [<span data-ttu-id="2f898-186">Teams で緊急通話のポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="2f898-186">Manage emergency calling policies in Teams</span></span>](manage-emergency-calling-policies.md)
- [<span data-ttu-id="2f898-187">Teams での PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="2f898-187">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="2f898-188">チームのユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="2f898-188">Assign policies to your users in Teams</span></span>](assign-policies.md)
