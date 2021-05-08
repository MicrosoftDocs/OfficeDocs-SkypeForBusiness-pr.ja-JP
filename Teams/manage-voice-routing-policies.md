---
title: 音声ルーティング ポリシーを管理する Microsoft Teams
author: cichur
ms.author: v-cichur
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
description: 音声ルーティング ポリシーを作成して管理する方法については、Microsoft Teams。
ms.openlocfilehash: ac856ef05d425208af43307ebe12ff0c4776ca51
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101073"
---
# <a name="manage-voice-routing-policies-in-microsoft-teams"></a><span data-ttu-id="eaf82-103">音声ルーティング ポリシーを管理する Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="eaf82-103">Manage voice routing policies in Microsoft Teams</span></span>

<span data-ttu-id="eaf82-104">組織内に[電話システム](direct-routing-landing-page.md)ダイレクト ルーティングを展開している場合は、音声ルーティング ポリシーを使用して、Teams と Skype for Business Online のユーザーがオンプレミスのテレフォニー インフラストラクチャを使用して公衆交換電話網 (PSTN) を受信および発信できます。</span><span class="sxs-lookup"><span data-stu-id="eaf82-104">If you've deployed [Phone System Direct Routing](direct-routing-landing-page.md) in your organization, you use voice routing policies to allow Teams and Skype for Business Online users to receive and make phone calls to the Public Switched Telephone Network (PSTN) using your on-premises telephony infrastructure.</span></span>

<span data-ttu-id="eaf82-105">音声ルーティング ポリシーは、PSTN 使用レコードのコンテナーです。</span><span class="sxs-lookup"><span data-stu-id="eaf82-105">A voice routing policy is a container for PSTN usage records.</span></span> <span data-ttu-id="eaf82-106">音声ルーティング ポリシーを作成および管理するには、Microsoft Teams管理センターで音声ルーティング ポリシーに移動するか  >  、Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="eaf82-106">You create and manage voice routing policies by going to **Voice** > **Voice routing policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span>

<span data-ttu-id="eaf82-107">グローバル (組織全体の既定) ポリシーを使用ことも、カスタム ポリシーを作成して割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="eaf82-107">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="eaf82-108">カスタム ポリシーを作成して割り当てない限り、ユーザーは自動的にグローバル ポリシーを取得します。</span><span class="sxs-lookup"><span data-stu-id="eaf82-108">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="eaf82-109">グローバル ポリシーの設定は編集できますが、名前の変更や削除はできないので、ご安心ください。</span><span class="sxs-lookup"><span data-stu-id="eaf82-109">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span>

<span data-ttu-id="eaf82-110">ユーザーに音声ルーティング ポリシーを割り当てると、ユーザーが PSTN 通話を行えなTeams。</span><span class="sxs-lookup"><span data-stu-id="eaf82-110">It's important to know that assigning a voice routing policy to a user doesn't enable them to make PSTN calls in Teams.</span></span> <span data-ttu-id="eaf82-111">また、ユーザーが直接ルーティングを実行電話システム、その他の構成手順を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eaf82-111">You'll also need to enable the user for Phone System Direct Routing and complete other configuration steps.</span></span> <span data-ttu-id="eaf82-112">詳細については、「ダイレクト ルーティングの [構成」を参照してください](direct-routing-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="eaf82-112">To learn more, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="create-a-custom-voice-routing-policy"></a><span data-ttu-id="eaf82-113">カスタム音声ルーティング ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="eaf82-113">Create a custom voice routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="eaf82-114">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="eaf82-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="eaf82-115">管理センターの左側のナビゲーションMicrosoft Teams Voice Voiceルーティング ポリシー] に移動し、[  >  追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="eaf82-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span><br>
    <span data-ttu-id="eaf82-116">![管理センターの [音声ルーティング ポリシーの追加] ページMicrosoft Teamsスクリーンショット](media/manage-voice-routing-policies.png)</span><span class="sxs-lookup"><span data-stu-id="eaf82-116">![Screenshot of the Add voice routing policy page in the Microsoft Teams admin center ](media/manage-voice-routing-policies.png)</span></span> 
2. <span data-ttu-id="eaf82-117">ポリシーの名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="eaf82-117">Enter a name and description for the policy.</span></span>
3. <span data-ttu-id="eaf82-118">[PSTN **利用状況レコード] で**、[PSTN 使用量の追加] **をクリック** し、追加するレコードを選択します。</span><span class="sxs-lookup"><span data-stu-id="eaf82-118">Under **PSTN usage records**, click **Add PSTN usage**, and then select the records that you want to add.</span></span> <span data-ttu-id="eaf82-119">新しい PSTN 使用レコードを作成する必要がある場合は、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="eaf82-119">If you need to create a new PSTN usage record, click **Add**.</span></span>
4. <span data-ttu-id="eaf82-120">複数の PSTN 使用レコードを追加した場合は、必要な順序で配置します。</span><span class="sxs-lookup"><span data-stu-id="eaf82-120">If you added multiple PSTN usage records, arrange them in the order that you want.</span></span>
5. <span data-ttu-id="eaf82-121">完了したら、[適用] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="eaf82-121">When you're done, click **Apply**.</span></span>
6. <span data-ttu-id="eaf82-122">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eaf82-122">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="eaf82-123">PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="eaf82-123">Using PowerShell</span></span>

<span data-ttu-id="eaf82-124">[New-CsOnlineVoiceRoutingPolicy を参照してください](/powershell/module/skype/new-csonlinevoiceroutingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="eaf82-124">See [New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy).</span></span>

## <a name="edit-a-voice-routing-policy"></a><span data-ttu-id="eaf82-125">音声ルーティング ポリシーを編集する</span><span class="sxs-lookup"><span data-stu-id="eaf82-125">Edit a voice routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="eaf82-126">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="eaf82-126">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="eaf82-127">グローバル ポリシー、または作成したカスタム ポリシーを編集できます。</span><span class="sxs-lookup"><span data-stu-id="eaf82-127">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="eaf82-128">管理センターの左側のナビゲーションMicrosoft Teams音声ルーティング ポリシー に  >  **移動します**。</span><span class="sxs-lookup"><span data-stu-id="eaf82-128">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**.</span></span>
2. <span data-ttu-id="eaf82-129">ポリシー名の左側をクリックしてポリシーを選び、**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eaf82-129">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="eaf82-130">[PSTN **使用レコードの追加/** 削除] をクリックし、必要な変更を加え、[保存] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="eaf82-130">Click **Add/remove PSTN usage records**, make the changes that you want, and then click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="eaf82-131">PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="eaf82-131">Using PowerShell</span></span>

<span data-ttu-id="eaf82-132">[「Set-CsOnlineVoiceRoutingPolicy」を参照してください](/powershell/module/skype/set-csonlinevoiceroutingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="eaf82-132">See [Set-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/set-csonlinevoiceroutingpolicy).</span></span>

## <a name="assign-a-custom-voice-routing-policy-to-users"></a><span data-ttu-id="eaf82-133">カスタム音声ルーティング ポリシーをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="eaf82-133">Assign a custom voice routing policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="eaf82-134">[Grant-CsOnlineVoiceRoutingPolicy も参照してください](/powershell/module/skype/grant-csonlinevoiceroutingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="eaf82-134">See also [Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy).</span></span>

## <a name="related-topics"></a><span data-ttu-id="eaf82-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="eaf82-135">Related topics</span></span>

[<span data-ttu-id="eaf82-136">Teams での PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="eaf82-136">Teams PowerShell overview</span></span>](teams-powershell-overview.md)

[<span data-ttu-id="eaf82-137">ダイレクト ルーティングの音声ルーティングを構成する</span><span class="sxs-lookup"><span data-stu-id="eaf82-137">Configure voice routing for Direct Routing</span></span>](direct-routing-voice-routing.md)

[<span data-ttu-id="eaf82-138">ダイレクト ルーティングの場所に基づくルーティングを有効にする</span><span class="sxs-lookup"><span data-stu-id="eaf82-138">Enable Location-Based Routing for Direct Routing</span></span>](location-based-routing-enable.md)

[<span data-ttu-id="eaf82-139"> Teams でユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="eaf82-139">Assign policies to your users in Teams</span></span>](assign-policies.md)