---
title: Microsoft Teams でボイスルーティングポリシーを管理する
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords: ''
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams でボイスルーティングポリシーを作成して管理する方法について説明します。
ms.openlocfilehash: 7fa2530e170d398598e56d4b4f846cc316871b16
ms.sourcegitcommit: 6e24ea8aa9cccf8a1a964c8ed414ef5c7de3dc17
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "44160979"
---
# <a name="manage-voice-routing-policies-in-microsoft-teams"></a><span data-ttu-id="87abf-103">Microsoft Teams でボイスルーティングポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="87abf-103">Manage voice routing policies in Microsoft Teams</span></span>

<span data-ttu-id="87abf-104">組織で[電話システムのダイレクトルーティング](direct-routing-landing-page.md)を展開した場合は、音声ルーティングポリシーを使用して、チームと Skype For business Online ユーザーがオンプレミスのテレフォニーインフラストラクチャを使って公衆交換電話網 (PSTN) に電話をかけたり、通話を発信したりできるようにします。</span><span class="sxs-lookup"><span data-stu-id="87abf-104">If you've deployed [Phone System Direct Routing](direct-routing-landing-page.md) in your organization, you use voice routing policies to allow Teams and Skype for Business Online users to receive and make phone calls to the Public Switched Telephone Network (PSTN) using your on-premises telephony infrastructure.</span></span>

<span data-ttu-id="87abf-105">ボイスルーティングポリシーは、PSTN 使用状況レコードのコンテナーです。</span><span class="sxs-lookup"><span data-stu-id="87abf-105">A voice routing policy is a container for PSTN usage records.</span></span> <span data-ttu-id="87abf-106">音声ルーティングのポリシーを作成して管理するには、Microsoft Teams 管理センターまたは Windows PowerShell を使用して**音声** > **音声ルーティングポリシー**に移動します。</span><span class="sxs-lookup"><span data-stu-id="87abf-106">You create and manage voice routing policies by going to **Voice** > **Voice routing policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span>

<span data-ttu-id="87abf-107">グローバル (組織全体の既定) ポリシーを使用するか、カスタムポリシーを作成して割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="87abf-107">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="87abf-108">カスタムポリシーを作成して割り当てる場合を除き、ユーザーはグローバルポリシーを自動的に取得します。</span><span class="sxs-lookup"><span data-stu-id="87abf-108">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="87abf-109">グローバルポリシーの設定は編集できますが、名前の変更や削除はできないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="87abf-109">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span>

<span data-ttu-id="87abf-110">ユーザーにボイスルーティングポリシーを割り当てることで、チームで PSTN 通話を発信することはできないことを知っておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="87abf-110">It's important to know that assigning a voice routing policy to a user doesn't enable them to make PSTN calls in Teams.</span></span> <span data-ttu-id="87abf-111">また、ユーザーが電話システムのダイレクトルーティングを有効にし、その他の構成手順を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="87abf-111">You'll also need to enable the user for Phone System Direct Routing and complete other configuration steps.</span></span> <span data-ttu-id="87abf-112">詳細については、「[直接ルーティングを構成](direct-routing-configure.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="87abf-112">To learn more, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="create-a-custom-voice-routing-policy"></a><span data-ttu-id="87abf-113">カスタムボイスルーティングポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="87abf-113">Create a custom voice routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="87abf-114">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="87abf-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="87abf-115">Microsoft Teams 管理センターの左のナビゲーションで、[**音声** > **音声ルーティングポリシー**] に移動し、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="87abf-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span><br>
    <span data-ttu-id="87abf-116">![Microsoft Teams 管理センターの [ボイスルーティングポリシーの追加] ページのスクリーンショット](media/manage-voice-routing-policies.png)</span><span class="sxs-lookup"><span data-stu-id="87abf-116">![Screenshot of the Add voice routing policy page in the Microsoft Teams admin center ](media/manage-voice-routing-policies.png)</span></span> 
2. <span data-ttu-id="87abf-117">ポリシーの名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="87abf-117">Enter a name and description for the policy.</span></span>
3. <span data-ttu-id="87abf-118">[ **Pstn 使用状況レコード**] の [ **pstn 使用量の追加**] をクリックし、追加するレコードを選択します。</span><span class="sxs-lookup"><span data-stu-id="87abf-118">Under **PSTN usage records**, click **Add PSTN usage**, and then select the records that you want to add.</span></span> <span data-ttu-id="87abf-119">新しい PSTN 使用状況レコードを作成する必要がある場合は、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="87abf-119">If you need to create a new PSTN usage record, click **Add**.</span></span>
4. <span data-ttu-id="87abf-120">複数の PSTN 利用状況レコードを追加した場合は、目的の順序に並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="87abf-120">If you added multiple PSTN usage records, arrange them in the order that you want.</span></span>
5. <span data-ttu-id="87abf-121">完了したら、[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="87abf-121">When you're done, click **Apply**.</span></span>
6. <span data-ttu-id="87abf-122">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="87abf-122">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="87abf-123">PowerShell を使用する場合</span><span class="sxs-lookup"><span data-stu-id="87abf-123">Using PowerShell</span></span>

<span data-ttu-id="87abf-124">「[新規-CsOnlineVoiceRoutingPolicy」を](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy)参照してください。</span><span class="sxs-lookup"><span data-stu-id="87abf-124">See [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy).</span></span>

## <a name="edit-a-voice-routing-policy"></a><span data-ttu-id="87abf-125">音声ルーティングポリシーを編集する</span><span class="sxs-lookup"><span data-stu-id="87abf-125">Edit a voice routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="87abf-126">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="87abf-126">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="87abf-127">グローバル ポリシー、または作成したカスタム ポリシーを編集できます。</span><span class="sxs-lookup"><span data-stu-id="87abf-127">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="87abf-128">Microsoft Teams 管理センターの左のナビゲーションで、[**音声** > **音声ルーティングポリシー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="87abf-128">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**.</span></span>
2. <span data-ttu-id="87abf-129">ポリシー名の左側をクリックしてポリシーを選び、**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="87abf-129">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="87abf-130">[ **PSTN 使用状況レコードの追加/削除**] をクリックし、必要な変更を加えて、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="87abf-130">Click **Add/remove PSTN usage records**, make the changes that you want, and then click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="87abf-131">PowerShell を使用する場合</span><span class="sxs-lookup"><span data-stu-id="87abf-131">Using PowerShell</span></span>

<span data-ttu-id="87abf-132">「 [Set-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceroutingpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="87abf-132">See [Set-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceroutingpolicy).</span></span>

## <a name="assign-a-custom-voice-routing-policy-to-users"></a><span data-ttu-id="87abf-133">カスタムボイスルーティングポリシーをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="87abf-133">Assign a custom voice routing policy to users</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="87abf-134">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="87abf-134">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="87abf-135">Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動してユーザーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="87abf-135">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="87abf-136">**[ポリシー]** をクリックし、**[割り当てられたポリシー]** の横にある **[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="87abf-136">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="87abf-137">[**音声ルーティングポリシー**] で、割り当てるポリシーを選択し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="87abf-137">Under **Voice routing policy**, select the policy you want to assign, and then click **Save**.</span></span>

<span data-ttu-id="87abf-138">一度に複数のユーザーにカスタムのチーム ポリシーを割り当てる方法については、「[一括で Teams のユーザー設定を編集する](edit-user-settings-in-bulk.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="87abf-138">To assign a custom teams policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="87abf-139">または、次の操作も実行できます。</span><span class="sxs-lookup"><span data-stu-id="87abf-139">Or, you can also do the following:</span></span>

1. <span data-ttu-id="87abf-140">Microsoft Teams 管理センターの左のナビゲーションで、[**音声** > **音声ルーティングポリシー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="87abf-140">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**.</span></span>
2. <span data-ttu-id="87abf-141">ポリシー名の左側をクリックしてポリシーを選びます。</span><span class="sxs-lookup"><span data-stu-id="87abf-141">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="87abf-142">[**ユーザーを管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="87abf-142">Select **Manage users**.</span></span>
4. <span data-ttu-id="87abf-143">[**ユーザーを管理**] ウィンドウで、表示名またはユーザー名でユーザーを検索し、名前を選択して [**追加**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="87abf-143">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="87abf-144">追加するユーザーごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="87abf-144">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="87abf-145">ユーザーの追加が完了したら、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="87abf-145">When you're finished adding users, click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="87abf-146">PowerShell を使用する場合</span><span class="sxs-lookup"><span data-stu-id="87abf-146">Using PowerShell</span></span>

<span data-ttu-id="87abf-147">「 [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="87abf-147">See [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy).</span></span>

## <a name="related-topics"></a><span data-ttu-id="87abf-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="87abf-148">Related topics</span></span>

- [<span data-ttu-id="87abf-149">Teams での PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="87abf-149">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="87abf-150">直接ルーティング用のボイスルーティングを構成する</span><span class="sxs-lookup"><span data-stu-id="87abf-150">Configure voice routing for Direct Routing</span></span>](direct-routing-voice-routing.md)
- [<span data-ttu-id="87abf-151">ダイレクト ルーティングの場所に基づくルーティングを有効にする</span><span class="sxs-lookup"><span data-stu-id="87abf-151">Enable Location-Based Routing for Direct Routing</span></span>](location-based-routing-enable.md)
