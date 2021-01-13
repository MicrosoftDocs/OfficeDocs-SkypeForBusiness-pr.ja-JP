---
title: Microsoft Teams で音声ルーティング ポリシーを管理する
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
description: Microsoft Teams で音声ルーティング ポリシーを作成および管理する方法について説明します。
ms.openlocfilehash: 00b70363f0034ebc8d99aa59e037658e406af2a5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802557"
---
# <a name="manage-voice-routing-policies-in-microsoft-teams"></a><span data-ttu-id="21284-103">Microsoft Teams で音声ルーティング ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="21284-103">Manage voice routing policies in Microsoft Teams</span></span>

<span data-ttu-id="21284-104">組織に電話システムダイレクト[](direct-routing-landing-page.md)ルーティングを展開している場合は、音声ルーティング ポリシーを使用して、Teams および Skype for Business Online ユーザーがオンプレミスのテレフォニー インフラストラクチャを使用して公衆交換電話網 (PSTN) を受信および発信できます。</span><span class="sxs-lookup"><span data-stu-id="21284-104">If you've deployed [Phone System Direct Routing](direct-routing-landing-page.md) in your organization, you use voice routing policies to allow Teams and Skype for Business Online users to receive and make phone calls to the Public Switched Telephone Network (PSTN) using your on-premises telephony infrastructure.</span></span>

<span data-ttu-id="21284-105">音声ルーティング ポリシーは、PSTN 使用状況レコードのコンテナーです。</span><span class="sxs-lookup"><span data-stu-id="21284-105">A voice routing policy is a container for PSTN usage records.</span></span> <span data-ttu-id="21284-106">音声ルーティング ポリシーを作成および管理するには、Microsoft Teams 管理センターで音声ルーティング ポリシーに移動するか、または  >  Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="21284-106">You create and manage voice routing policies by going to **Voice** > **Voice routing policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span>

<span data-ttu-id="21284-107">グローバル (組織全体の既定) ポリシーを使用するか、カスタム ポリシーを作成して割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="21284-107">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="21284-108">カスタム ポリシーを作成して割り当てない限り、ユーザーは自動的にグローバル ポリシーを取得します。</span><span class="sxs-lookup"><span data-stu-id="21284-108">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="21284-109">グローバル ポリシーの設定は編集できますが、名前の変更や削除はできないので、ご安心ください。</span><span class="sxs-lookup"><span data-stu-id="21284-109">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span>

<span data-ttu-id="21284-110">ユーザーに音声ルーティング ポリシーを割り当てると、Teams で PSTN 通話を発信できないという点を知る必要があります。</span><span class="sxs-lookup"><span data-stu-id="21284-110">It's important to know that assigning a voice routing policy to a user doesn't enable them to make PSTN calls in Teams.</span></span> <span data-ttu-id="21284-111">また、ユーザーが電話システムダイレクト ルーティングを有効にし、その他の構成手順を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="21284-111">You'll also need to enable the user for Phone System Direct Routing and complete other configuration steps.</span></span> <span data-ttu-id="21284-112">詳細については、「ダイレクト ルーティングの [構成」を参照してください](direct-routing-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="21284-112">To learn more, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="create-a-custom-voice-routing-policy"></a><span data-ttu-id="21284-113">カスタム音声ルーティング ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="21284-113">Create a custom voice routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="21284-114">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="21284-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="21284-115">Microsoft Teams 管理センターの左側のナビゲーションで、[**音声** ルーティング ポリシー] に移動し、[追加] を  >  クリック **します**。</span><span class="sxs-lookup"><span data-stu-id="21284-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span><br>
    <span data-ttu-id="21284-116">![Microsoft Teams 管理センターの [音声ルーティング ポリシーの追加] ページのスクリーンショット ](media/manage-voice-routing-policies.png)</span><span class="sxs-lookup"><span data-stu-id="21284-116">![Screenshot of the Add voice routing policy page in the Microsoft Teams admin center ](media/manage-voice-routing-policies.png)</span></span> 
2. <span data-ttu-id="21284-117">ポリシーの名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="21284-117">Enter a name and description for the policy.</span></span>
3. <span data-ttu-id="21284-118">**[PSTN 使用状況レコード] で**、[PSTN 使用状況の追加]**をクリック** し、追加するレコードを選択します。</span><span class="sxs-lookup"><span data-stu-id="21284-118">Under **PSTN usage records**, click **Add PSTN usage**, and then select the records that you want to add.</span></span> <span data-ttu-id="21284-119">新しい PSTN 使用状況レコードを作成する必要がある場合は、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="21284-119">If you need to create a new PSTN usage record, click **Add**.</span></span>
4. <span data-ttu-id="21284-120">複数の PSTN 使用状況レコードを追加した場合は、必要な順序で配置します。</span><span class="sxs-lookup"><span data-stu-id="21284-120">If you added multiple PSTN usage records, arrange them in the order that you want.</span></span>
5. <span data-ttu-id="21284-121">完了したら、[適用] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="21284-121">When you're done, click **Apply**.</span></span>
6. <span data-ttu-id="21284-122">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="21284-122">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="21284-123">PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="21284-123">Using PowerShell</span></span>

<span data-ttu-id="21284-124">[New-CsOnlineVoiceRoutingPolicy を参照してください](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="21284-124">See [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy).</span></span>

## <a name="edit-a-voice-routing-policy"></a><span data-ttu-id="21284-125">音声ルーティング ポリシーを編集する</span><span class="sxs-lookup"><span data-stu-id="21284-125">Edit a voice routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="21284-126">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="21284-126">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="21284-127">グローバル ポリシー、または作成したカスタム ポリシーを編集できます。</span><span class="sxs-lookup"><span data-stu-id="21284-127">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="21284-128">Microsoft Teams 管理センターの左側のナビゲーションで、[音声 **ルーティング** ポリシー  >  **] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="21284-128">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**.</span></span>
2. <span data-ttu-id="21284-129">ポリシー名の左側をクリックしてポリシーを選び、**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="21284-129">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="21284-130">[PSTN **使用状況レコードの追加/削除**] をクリックし、必要な変更を加え、[保存] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="21284-130">Click **Add/remove PSTN usage records**, make the changes that you want, and then click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="21284-131">PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="21284-131">Using PowerShell</span></span>

<span data-ttu-id="21284-132">[「Set-CsOnlineVoiceRoutingPolicy」を参照してください](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceroutingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="21284-132">See [Set-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceroutingpolicy).</span></span>

## <a name="assign-a-custom-voice-routing-policy-to-users"></a><span data-ttu-id="21284-133">カスタム音声ルーティング ポリシーをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="21284-133">Assign a custom voice routing policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="21284-134">[Grant-CsOnlineVoiceRoutingPolicy も参照してください](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="21284-134">See also [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy).</span></span>

## <a name="related-topics"></a><span data-ttu-id="21284-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="21284-135">Related topics</span></span>

[<span data-ttu-id="21284-136">Teams での PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="21284-136">Teams PowerShell overview</span></span>](teams-powershell-overview.md)

[<span data-ttu-id="21284-137">ダイレクト ルーティングの音声ルーティングを構成する</span><span class="sxs-lookup"><span data-stu-id="21284-137">Configure voice routing for Direct Routing</span></span>](direct-routing-voice-routing.md)

[<span data-ttu-id="21284-138">ダイレクト ルーティングの場所に基づくルーティングを有効にする</span><span class="sxs-lookup"><span data-stu-id="21284-138">Enable Location-Based Routing for Direct Routing</span></span>](location-based-routing-enable.md)

[<span data-ttu-id="21284-139"> Teams でユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="21284-139">Assign policies to your users in Teams</span></span>](assign-policies.md)
