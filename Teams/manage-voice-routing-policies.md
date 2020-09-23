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
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams でボイスルーティングポリシーを作成して管理する方法について説明します。
ms.openlocfilehash: 2bef422f22dc212b2c615e2ca2ab98806b396e9f
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217658"
---
# <a name="manage-voice-routing-policies-in-microsoft-teams"></a><span data-ttu-id="20ec7-103">Microsoft Teams でボイスルーティングポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="20ec7-103">Manage voice routing policies in Microsoft Teams</span></span>

<span data-ttu-id="20ec7-104">組織で [電話システムのダイレクトルーティング](direct-routing-landing-page.md) を展開した場合は、音声ルーティングポリシーを使用して、チームと Skype For business Online ユーザーがオンプレミスのテレフォニーインフラストラクチャを使って公衆交換電話網 (PSTN) に電話をかけたり、通話を発信したりできるようにします。</span><span class="sxs-lookup"><span data-stu-id="20ec7-104">If you've deployed [Phone System Direct Routing](direct-routing-landing-page.md) in your organization, you use voice routing policies to allow Teams and Skype for Business Online users to receive and make phone calls to the Public Switched Telephone Network (PSTN) using your on-premises telephony infrastructure.</span></span>

<span data-ttu-id="20ec7-105">ボイスルーティングポリシーは、PSTN 使用状況レコードのコンテナーです。</span><span class="sxs-lookup"><span data-stu-id="20ec7-105">A voice routing policy is a container for PSTN usage records.</span></span> <span data-ttu-id="20ec7-106">音声ルーティングのポリシーを作成して管理する**Voice**に  >  は、Microsoft Teams 管理センターまたは Windows PowerShell を使用して音声**音声ルーティングポリシー**に移動します。</span><span class="sxs-lookup"><span data-stu-id="20ec7-106">You create and manage voice routing policies by going to **Voice** > **Voice routing policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span>

<span data-ttu-id="20ec7-107">グローバル (組織全体の既定) ポリシーを使用するか、カスタムポリシーを作成して割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="20ec7-107">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="20ec7-108">カスタムポリシーを作成して割り当てる場合を除き、ユーザーはグローバルポリシーを自動的に取得します。</span><span class="sxs-lookup"><span data-stu-id="20ec7-108">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="20ec7-109">グローバルポリシーの設定は編集できますが、名前の変更や削除はできないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="20ec7-109">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span>

<span data-ttu-id="20ec7-110">ユーザーにボイスルーティングポリシーを割り当てることで、チームで PSTN 通話を発信することはできないことを知っておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="20ec7-110">It's important to know that assigning a voice routing policy to a user doesn't enable them to make PSTN calls in Teams.</span></span> <span data-ttu-id="20ec7-111">また、ユーザーが電話システムのダイレクトルーティングを有効にし、その他の構成手順を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="20ec7-111">You'll also need to enable the user for Phone System Direct Routing and complete other configuration steps.</span></span> <span data-ttu-id="20ec7-112">詳細については、「 [直接ルーティングを構成](direct-routing-configure.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="20ec7-112">To learn more, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="create-a-custom-voice-routing-policy"></a><span data-ttu-id="20ec7-113">カスタムボイスルーティングポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="20ec7-113">Create a custom voice routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="20ec7-114">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="20ec7-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="20ec7-115">Microsoft Teams 管理センターの左のナビゲーションで、[**音声**  >  **音声ルーティングポリシー**] に移動し、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="20ec7-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span><br>
    <span data-ttu-id="20ec7-116">![Microsoft Teams 管理センターの [ボイスルーティングポリシーの追加] ページのスクリーンショット ](media/manage-voice-routing-policies.png)</span><span class="sxs-lookup"><span data-stu-id="20ec7-116">![Screenshot of the Add voice routing policy page in the Microsoft Teams admin center ](media/manage-voice-routing-policies.png)</span></span> 
2. <span data-ttu-id="20ec7-117">ポリシーの名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="20ec7-117">Enter a name and description for the policy.</span></span>
3. <span data-ttu-id="20ec7-118">[ **Pstn 使用状況レコード**] の [ **pstn 使用量の追加**] をクリックし、追加するレコードを選択します。</span><span class="sxs-lookup"><span data-stu-id="20ec7-118">Under **PSTN usage records**, click **Add PSTN usage**, and then select the records that you want to add.</span></span> <span data-ttu-id="20ec7-119">新しい PSTN 使用状況レコードを作成する必要がある場合は、[ **追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="20ec7-119">If you need to create a new PSTN usage record, click **Add**.</span></span>
4. <span data-ttu-id="20ec7-120">複数の PSTN 利用状況レコードを追加した場合は、目的の順序に並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="20ec7-120">If you added multiple PSTN usage records, arrange them in the order that you want.</span></span>
5. <span data-ttu-id="20ec7-121">完了したら、[ **適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="20ec7-121">When you're done, click **Apply**.</span></span>
6. <span data-ttu-id="20ec7-122">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="20ec7-122">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="20ec7-123">PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="20ec7-123">Using PowerShell</span></span>

<span data-ttu-id="20ec7-124">「 [新規-CsOnlineVoiceRoutingPolicy」を](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy)参照してください。</span><span class="sxs-lookup"><span data-stu-id="20ec7-124">See [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy).</span></span>

## <a name="edit-a-voice-routing-policy"></a><span data-ttu-id="20ec7-125">音声ルーティングポリシーを編集する</span><span class="sxs-lookup"><span data-stu-id="20ec7-125">Edit a voice routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="20ec7-126">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="20ec7-126">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="20ec7-127">グローバル ポリシー、または作成したカスタム ポリシーを編集できます。</span><span class="sxs-lookup"><span data-stu-id="20ec7-127">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="20ec7-128">Microsoft Teams 管理センターの左のナビゲーションで、[**音声**  >  **音声ルーティングポリシー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="20ec7-128">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**.</span></span>
2. <span data-ttu-id="20ec7-129">ポリシー名の左側をクリックしてポリシーを選び、**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="20ec7-129">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="20ec7-130">[ **PSTN 使用状況レコードの追加/削除**] をクリックし、必要な変更を加えて、[ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="20ec7-130">Click **Add/remove PSTN usage records**, make the changes that you want, and then click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="20ec7-131">PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="20ec7-131">Using PowerShell</span></span>

<span data-ttu-id="20ec7-132">「 [Set-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceroutingpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="20ec7-132">See [Set-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceroutingpolicy).</span></span>

## <a name="assign-a-custom-voice-routing-policy-to-users"></a><span data-ttu-id="20ec7-133">カスタムボイスルーティングポリシーをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="20ec7-133">Assign a custom voice routing policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="20ec7-134">「 [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy)」も参照してください。</span><span class="sxs-lookup"><span data-stu-id="20ec7-134">See also [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy).</span></span>

## <a name="related-topics"></a><span data-ttu-id="20ec7-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="20ec7-135">Related topics</span></span>

[<span data-ttu-id="20ec7-136">Teams での PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="20ec7-136">Teams PowerShell overview</span></span>](teams-powershell-overview.md)

[<span data-ttu-id="20ec7-137">直接ルーティング用のボイスルーティングを構成する</span><span class="sxs-lookup"><span data-stu-id="20ec7-137">Configure voice routing for Direct Routing</span></span>](direct-routing-voice-routing.md)

[<span data-ttu-id="20ec7-138">ダイレクト ルーティングの場所に基づくルーティングを有効にする</span><span class="sxs-lookup"><span data-stu-id="20ec7-138">Enable Location-Based Routing for Direct Routing</span></span>](location-based-routing-enable.md)

[<span data-ttu-id="20ec7-139">チームのユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="20ec7-139">Assign policies to your users in Teams</span></span>](assign-policies.md)
