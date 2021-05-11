---
title: Microsoft Teams で発信者番号ポリシーを管理する
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: roykuntz; jens
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.voice.callinglineid.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams で発信者番号ポリシーを使用および管理して、組織内の Teams ユーザーの発信者番号を変更またはブロックする方法について説明します。
ms.openlocfilehash: cd928af5213a1e6fa927662adaba0fefecb687d5
ms.sourcegitcommit: 83f14c4c79559ef28357ff076938e52b369fc0c7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2021
ms.locfileid: "52308376"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a><span data-ttu-id="4ecc1-103">Microsoft Teams で発信者番号ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="4ecc1-103">Manage caller ID policies in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="4ecc1-104">呼び出し元 ID をリソース アカウントの電話番号に設定し、発信者名を設定するには、Teams PowerShell モジュール 2.3.1 以降の PowerShell コマンドレット New-CsCallingLineIdentity または Set-CsCallingLineIdentity を使用します。</span><span class="sxs-lookup"><span data-stu-id="4ecc1-104">To set the caller ID to a resource account phone number and to set the calling party name, use the PowerShell cmdlets New-CsCallingLineIdentity or Set-CsCallingLineIdentity in the Teams PowerShell module 2.3.1 or later.</span></span> <span data-ttu-id="4ecc1-105">(これらのオプションは現在、管理センター Microsoft Teams使用できません)。</span><span class="sxs-lookup"><span data-stu-id="4ecc1-105">(These options are not currently available in the Microsoft Teams admin center.)</span></span> 

<span data-ttu-id="4ecc1-106">既定では、ユーザーが PSTN Teams通話を行った場合、ユーザーの電話番号Teams表示されます。</span><span class="sxs-lookup"><span data-stu-id="4ecc1-106">By default, when a Teams user makes a call to a PSTN phone, the phone number of the Teams user is visible.</span></span> <span data-ttu-id="4ecc1-107">同様に、PSTN 発信者がユーザーに通話を発信Teams PSTN 発信者の電話番号が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4ecc1-107">Likewise, when a PSTN caller makes a call to a Teams user, the PSTN caller's phone number is visible.</span></span>

<span data-ttu-id="4ecc1-108">管理者は、発信者番号ポリシーを使用して、発信者番号 (通話回線 ID とも呼ばれる) を変更またはブロックできます。</span><span class="sxs-lookup"><span data-stu-id="4ecc1-108">As an administrator, you can use caller ID policies to change or block the caller ID (also known as calling line ID).</span></span> <span data-ttu-id="4ecc1-109">発信者番号ポリシーを使用して、組織内の Teams ユーザーの代替電話番号を表示したり、発信電話番号をブロックしたり、着信番号の表示をブロックしたり、発信者名 (CNAM) を設定したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="4ecc1-109">You can use caller ID policies to display an alternate phone number for Teams users in your organization, block the outbound phone number, block an incoming number from being displayed, or set the Calling Party Name (CNAM).</span></span> <span data-ttu-id="4ecc1-110">たとえば、ユーザーが通話を行う場合、発信者番号を変更して、ユーザーの電話番号の代わりに組織のメイン電話番号と会社名を表示できます。</span><span class="sxs-lookup"><span data-stu-id="4ecc1-110">For example, when a user makes a call, you can change the caller ID to display your organization's main phone number and company name instead of the user's phone number.</span></span>

<span data-ttu-id="4ecc1-111">発信者番号ポリシーを管理するには、Microsoft Teams 管理センターで **[音声]** > **[発信者番号ポリシー]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="4ecc1-111">You manage caller ID policies by going to **Voice** > **Caller ID policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="4ecc1-112">グローバル (組織全体の既定) ポリシーを使用ことも、カスタム ポリシーを作成して割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="4ecc1-112">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="4ecc1-113">カスタム ポリシーを作成して割り当てていない場合、組織内のユーザーにはグローバル ポリシーが自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="4ecc1-113">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

## <a name="create-a-custom-caller-id-policy"></a><span data-ttu-id="4ecc1-114">カスタム発信者番号ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="4ecc1-114">Create a custom caller ID policy</span></span>

1. <span data-ttu-id="4ecc1-115">Microsoft Teams 管理センターの左側のナビゲーションで、**[音声]** > **[発信者番号ポリシー]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="4ecc1-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="4ecc1-116">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4ecc1-116">Click **Add**.</span></span> <br>
<span data-ttu-id="4ecc1-117">![管理センターの新しい [発信者番号ポリシー] ページのスクリーン ショット](media/caller-id-policies-add-policy.png)</span><span class="sxs-lookup"><span data-stu-id="4ecc1-117">![Screenshot of new caller ID policy page in the admin center](media/caller-id-policies-add-policy.png)</span></span>
3. <span data-ttu-id="4ecc1-118">ポリシーの名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="4ecc1-118">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="4ecc1-119">ここで、希望する設定を選びます。</span><span class="sxs-lookup"><span data-stu-id="4ecc1-119">From here, choose the settings that you want:</span></span>

    - <span data-ttu-id="4ecc1-120">**[着信した発信者番号をブロックする]**: この設定をオンにすると、着信した通話の発信者番号が表示されないようにブロックされます。</span><span class="sxs-lookup"><span data-stu-id="4ecc1-120">**Block incoming caller ID**: Turn on this setting to block the caller ID of incoming calls from being displayed.</span></span>
    - <span data-ttu-id="4ecc1-121">**[発信者番号ポリシーの上書き]**: この設定をオンにすると、ユーザーは自分の番号が受信者に表示されるかどうかに関するポリシーの設定を上書きすることができます。</span><span class="sxs-lookup"><span data-stu-id="4ecc1-121">**Override the caller ID policy**: Turn on this setting to let users override the settings in the policy regarding displaying their number to callees or not.</span></span> <span data-ttu-id="4ecc1-122">つまり、発信者番号を表示するかどうかをユーザー自身が選択できます。</span><span class="sxs-lookup"><span data-stu-id="4ecc1-122">This means that users can choose whether to display their caller ID.</span></span> <span data-ttu-id="4ecc1-123">詳細については、「[発信者番号のエンド ユーザー制御](./how-can-caller-id-be-used-in-your-organization.md#end-user-control-of-outbound-caller-id)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ecc1-123">For more information, see [End user control of outbound caller ID](./how-can-caller-id-be-used-in-your-organization.md#end-user-control-of-outbound-caller-id).</span></span>
    - <span data-ttu-id="4ecc1-124">**[発信者番号を置換する]**: 次のいずれかを選択して、ユーザーに対して表示される発信者番号を設定します。</span><span class="sxs-lookup"><span data-stu-id="4ecc1-124">**Replace the caller ID with**: Set the caller ID to be displayed for users by selecting one of the following:</span></span>

        - <span data-ttu-id="4ecc1-125">**[ユーザーの番号]**: ユーザーの番号を表示します。</span><span class="sxs-lookup"><span data-stu-id="4ecc1-125">**User's number**: Displays the user's number.</span></span> 
        - <span data-ttu-id="4ecc1-126">**[サービス番号]**: サービス電話番号が発信者番号として表示されるように設定できるようになります。</span><span class="sxs-lookup"><span data-stu-id="4ecc1-126">**Service number**: Lets you set a service phone number to display as the caller ID.</span></span>
        - <span data-ttu-id="4ecc1-127">**[匿名]**: 発信者番号が [匿名] として表示されます。</span><span class="sxs-lookup"><span data-stu-id="4ecc1-127">**Anonymous**: Displays the caller ID as Anonymous.</span></span>

    - <span data-ttu-id="4ecc1-128">**[発信者番号をこのサービス番号に置換する]**: ユーザーの発信者番号の代わりに使用するサービス番号を選択します。</span><span class="sxs-lookup"><span data-stu-id="4ecc1-128">**Replace the caller ID with this service number**: Choose a service number to replace the caller ID of users.</span></span> <span data-ttu-id="4ecc1-129">このオプションは、**[発信者番号を置換する]** で **[サービス番号]** を選択した場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="4ecc1-129">This option is available if you selected **Service number** in **Replace the caller ID with**.</span></span>

5. <span data-ttu-id="4ecc1-130">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4ecc1-130">Click **Save**.</span></span>

## <a name="edit-a-caller-id-policy"></a><span data-ttu-id="4ecc1-131">発信者番号ポリシーを編集する</span><span class="sxs-lookup"><span data-stu-id="4ecc1-131">Edit a caller ID policy</span></span>

<span data-ttu-id="4ecc1-132">グローバル ポリシー、または作成したカスタム ポリシーを編集できます。</span><span class="sxs-lookup"><span data-stu-id="4ecc1-132">You can edit the global policy or any custom policies that you create.</span></span> 

1. <span data-ttu-id="4ecc1-133">Microsoft Teams 管理センターの左側のナビゲーションで、**[音声]** > **[発信者番号ポリシー]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="4ecc1-133">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="4ecc1-134">ポリシー名の左側をクリックしてポリシーを選び、**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4ecc1-134">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="4ecc1-135">目的に合わせて設定を変更したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4ecc1-135">Change the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-caller-id-policy-to-users"></a><span data-ttu-id="4ecc1-136">カスタム発信者番号ポリシーをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="4ecc1-136">Assign a custom caller ID policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a><span data-ttu-id="4ecc1-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="4ecc1-137">Related topics</span></span>

[<span data-ttu-id="4ecc1-138">New-CsCallingLineIdentity</span><span class="sxs-lookup"><span data-stu-id="4ecc1-138">New-CsCallingLineIdentity</span></span>](/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)

[<span data-ttu-id="4ecc1-139">Set-CsCallingLineIdentity</span><span class="sxs-lookup"><span data-stu-id="4ecc1-139">Set-CsCallingLineIdentity</span></span>](/powershell/module/skype/set-cscallinglineidentity?view=skype-ps)

[<span data-ttu-id="4ecc1-140"> Teams でユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="4ecc1-140">Assign policies to your users in Teams</span></span>](assign-policies.md)